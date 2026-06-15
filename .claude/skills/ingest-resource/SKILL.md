---
name: ingest-resource
description: Systematically bring an external resource (article URL, file attachment, YouTube video, transcript, or raw notes) into the personal operating system at /home/user/Claude. Detects the source type, fetches/reads the content, summarizes it, files it in the correct Knowledge/ subfolder, and cross-references related existing material. Use whenever the user wants to capture something external so it's searchable and tied into existing knowledge.
---

# Ingest Resource

Bring an external resource into the `Knowledge/` tree of this personal operating
system as a clean, summarized, cross-referenced markdown note.

## Step 1 — Detect the source type

Look at what was passed in `args` (or what the user attached/pasted) and classify it:

- **URL — article/webpage**: a generic `http(s)://` link to a blog post, news
  article, documentation page, etc.
- **URL — YouTube video**: a `youtube.com` or `youtu.be` link.
- **File attachment**: PDF, DOCX, image, etc. provided as a local path under
  `/root/.claude/uploads/...` or similar.
- **Transcript**: a long block of raw transcript text (e.g. pasted from a call,
  podcast, or video) — usually unstructured, speaker-labeled, or very long.
- **Notes**: short-to-medium freeform text the user typed or pasted directly —
  their own thoughts, not a third-party transcript.

If the type is ambiguous, ask the user one short clarifying question before
proceeding (e.g. "Is this your own notes, or a transcript of someone else's
talk?").

## Step 2 — Fetch or read the content

- **Article URL**: Use `WebFetch` to retrieve the page content.
- **YouTube URL**: Use `WebFetch` on the URL to get title/description/metadata.
  If a transcript isn't directly accessible, summarize based on whatever
  metadata and description is available, and note in the file that the full
  transcript wasn't retrievable.
- **File attachment**:
  - PDF: use `Read` (use the `pages` parameter for large PDFs, max 20 pages per
    call). If `Read` reports `pdftoppm`/`pdftotext` missing, install
    `poppler-utils` via `Bash` (`apt-get update && apt-get install -y
    poppler-utils`), then retry. For text-based PDFs prefer
    `pdftotext -layout` for speed; for image-based PDFs render pages with
    `pdftoppm -png` and `Read` the resulting images.
  - DOCX: unzip with `Bash` (`unzip -o -q file.docx -d /tmp/extract_X`) and
    extract text from `word/document.xml` with a small Python snippet that
    pulls `<w:t>` runs (same approach used previously in this repo).
  - Images: `Read` directly — the model can view images natively.
- **Transcript / Notes pasted in chat**: the content is already in context —
  no fetch needed.

## Step 3 — Summarize it

Produce a markdown note with this structure:

```markdown
# <Title>

**Source**: <URL, file name, or "Personal notes">
**Type**: Article | Video | Transcript | Notes | Document
**Date ingested**: <YYYY-MM-DD>

## Summary
<3-8 sentence summary capturing the core argument/content>

## Key Points
- <bullet list of the most important points, claims, or takeaways>

## Relevance
<1-3 sentences on why this matters / how it connects to the user's work,
goals, or existing knowledge — informed by Knowledge/me/ and the destination
folder's existing files>

## Related Notes
- <links to related files in Knowledge/, added in Step 5>
```

Keep the summary genuinely useful — dense and skimmable, not a generic
restatement. Preserve specific facts, numbers, names, and quotes that would be
lost if paraphrased too loosely.

Use today's date (see `currentDate` in the session context) for "Date
ingested".

## Step 4 — File it in the right Knowledge/ subfolder

Decide the destination based on content, not source type:

- **`Knowledge/me/`** — personal reflections, the user's own notes about
  goals/identity/work style, content about Garth specifically.
- **`Knowledge/LeapLab/`** — anything about LeapLab: product, team, market,
  competitors, ongoing initiatives.
- **`Knowledge/Frameworks/`** — mental models, methodologies, decision-making
  frameworks, productivity/business/personal-development frameworks that the
  user could apply repeatedly.
- **`Knowledge/General/`** — everything else (general reference material,
  industry news, miscellaneous learning).

If a resource is genuinely Project-specific (e.g. clearly tied to an existing
folder under `projects/`), prefer filing it there instead and note that
choice to the user.

Naming convention: `Knowledge/<Folder>/<kebab-case-title>.md`. Check for
existing files with similar names first — if this is clearly an update to
something already ingested, ask the user whether to update the existing file
or create a new one rather than silently duplicating.

If the destination folder only contains a `.gitkeep` placeholder, remove the
placeholder once real content is added.

## Step 5 — Cross-reference related material

Before finishing:

1. `Grep` across `Knowledge/` for key terms, names, and topics from the new
   note to find related existing files.
2. Add a short "Related Notes" section (see Step 3 template) in the new file
   linking to relevant existing files by relative path.
3. For any existing file that's strongly related (not just tangentially), add
   a brief back-link to the new note — a one-line addition under a "Related
   Notes" or "See also" section, creating one if it doesn't exist. Don't
   rewrite or restructure existing files beyond this small addition.

## Step 6 — Confirm and commit

1. Show the user a short summary of what was filed: title, destination path,
   and any cross-links created.
2. Stage and commit the new/updated files with a descriptive commit message
   (e.g. `Ingest "<title>" into Knowledge/<Folder>`).
3. Push to the current branch following this repo's normal git workflow.

## Notes

- If the resource is large (long article, long transcript), summarize —
  don't paste the full raw content into the knowledge file. Link out to the
  original URL/source instead.
- If fetching a URL fails (paywall, login-gated, blocked), tell the user and
  ask whether they can paste the content directly.
- Always read `Knowledge/me/` context as needed to judge relevance, but don't
  re-summarize it — it's there for reference, not as input material.
