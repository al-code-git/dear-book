# dear-book

A personal collection of book summaries, one Markdown file per book.

## Adding a new summary

1. **Pick the category folder** at the repo root (e.g. `programming/`, `theological/`, `romance/`). If the book doesn't fit an existing category, create a new lowercase-kebab-case folder for it (e.g. `business/`, `fiction/`, `biography/`) rather than forcing it into a mismatched one.
2. **Copy the template**: start new files from [templates/summary-template.md](templates/summary-template.md).
3. **Name the file**: `<title-slug>.<lang>.md`
   - `title-slug` is the book title in lowercase kebab-case, ASCII only (no `&`, no punctuation beyond hyphens — special characters like `&` cause problems in git/Windows paths).
   - `lang` is the ISO 639-1 code of the language the *summary* is written in (`en`, `pt`, `es`, ...).
   - Example: `fundamentals-of-software-architecture.en.md`, `dom-casmurro.pt.md`.
   - If you summarize the same book in two languages, they become two files differing only by the language suffix — never overwrite one with the other.
4. **Add the cover image, if you have one**: place it at `<category>/covers/<title-slug>.<lang>.<ext>` (`ext` is `jpg`, `png`, etc. — whatever the source image is, don't transcode). Example: `theological/covers/o-verdadeiro-evangelho.pt.jpg`.
5. **Fill in the front-matter** at the top of the file:
   ```yaml
   ---
   title: Fundamentals of Software Architecture
   author: Mark Richards & Neal Ford
   category: programming
   language: en
   pages: 480
   cover: covers/fundamentals-of-software-architecture.en.jpg
   date_finished: 2024-03-15
   tags: [software-architecture]
   rating: 4
   ---
   ```
   - `title`, `author`, `category`, `language` are required. `category` must match the folder name.
   - `pages`, `cover`, `date_finished`, `tags`, `rating` are optional — leave blank/empty if unknown rather than guessing.
   - `cover` is a path relative to the summary file itself (i.e. relative to the category folder), so it's just `covers/<filename>`.
6. **Update the index in [README.md](README.md)**: add a row to the table for the matching category with a relative link to the new file, and a thumbnail if a cover exists.

## Conventions recap

- One file per book. Folder = category. Filename = `<title-slug>.<lang>.md`.
- Every file has YAML front-matter with at least `title`, `author`, `category`, `language`.
- Cover images live in `<category>/covers/`, named like the summary they belong to, referenced by the `cover` front-matter field.
- Keep filenames ASCII/kebab-case — avoid spaces, `&`, and other special characters.
- Don't invent new front-matter fields or restructure existing summaries without being asked.
