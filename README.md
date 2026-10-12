# Bowen Yang academic website

A lightweight Jekyll website adapted from al-folio’s classic about-page structure. Includes Home, Research, Publications, Projects, People, Teaching, News, Openings, and CV / Contact. Content guidance is intentionally visible until you replace it with your own text.

This is a reduced, standalone adaptation, not the full al-folio starter or its v1 plugin runtime. The about layout is derived from al-folio v0.14.0; the other layouts and local stylesheet are simplified for this site. There is no JavaScript, Node build, Bootstrap, external font, analytics, image-processing service, blog, search, or citation-metric integration. Jekyll Scholar is retained for BibTeX publications. See THIRD_PARTY_NOTICES.md for provenance.

## Start here

1. Read MAINTENANCE.md for setup, publishing, content edits, layout changes, and troubleshooting.
2. Work through CONTENT_CHECKLIST.md before publishing.
3. Run `bundle install`, then `bundle exec jekyll serve` from this folder. Open http://127.0.0.1:4000.

The package is designed to become the **root contents** of your own `YOUR-USERNAME.github.io` repository. Do not upload the outer workspace or materials_reference folder. No reference DOCX files are copied into the public site.

## File map

| File or folder | Purpose |
| --- | --- |
| `_config.yml` | Identity, public contact, domain, CV path, build settings |
| `index.md` | Home introduction, portrait settings, section order |
| `_pages/` | Eight additional pages and their content |
| `_data/navigation.yml` | Navigation labels and order |
| `_data/news.yml` | Shared news entries |
| `_bibliography/papers.bib` | Publication source |
| `_layouts/` | HTML shells and publication rendering |
| `_includes/` | Reusable figures, news, and home sections |
| `assets/css/main.css` | Appearance and responsive layout |
| `assets/img/`, `assets/pdf/` | Your public images and downloads |
| `.github/workflows/pages.yml` | GitHub Actions build and deployment |
| `Gemfile`, `Gemfile.lock` | Ruby dependencies and pinned versions |

Reference material was used to choose headings and content prompts, not to publish a detailed biography or complete publication record. Confirm the short role and affiliation in `_config.yml` before launch.
