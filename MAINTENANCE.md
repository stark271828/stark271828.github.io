# Website maintenance and layout guide

## 1. How this website works

You edit Markdown, YAML settings, and BibTeX. Jekyll turns those into HTML in `_site`. GitHub Actions builds the same source and uploads the generated website to GitHub Pages. Visitors only receive static HTML, CSS, images, and PDFs.

This package is a reduced al-folio adaptation with local templates, not the complete upstream template. Keep its structure small and add features only when needed. Dependencies are Jekyll, Jekyll Scholar, a local web server, and Ruby compatibility helpers. No npm commands are needed.

All commands below run **inside web_by_academic**, or inside the repository containing its contents after you publish it. Keep `Gemfile.lock` in version control. Generated `_site` and caches are ignored; never edit generated HTML as your source.

## 2. Preview on Windows

Install Ruby with Devkit from https://rubyinstaller.org if it is not installed. Ruby 3.4 matches the deployment workflow. Open PowerShell in the site folder:

```powershell
bundle install
bundle exec jekyll serve --host 127.0.0.1
```

Open http://127.0.0.1:4000. Leave the terminal running while editing; pages normally rebuild automatically. Press Ctrl+C to stop. Restart the server after changing `_config.yml`. For a build without a server:

```powershell
$env:JEKYLL_ENV = 'production'
bundle exec jekyll build --trace
```

The initial site intentionally displays guidance text and figure boxes. They are editable placeholders, not finished application text.

## 3. Publish to your GitHub account domain

1. Find your exact GitHub username. Create your own repository named `YOUR-USERNAME.github.io` using the lowercase username. The address will be `https://YOUR-USERNAME.github.io`.
2. Set `_config.yml`:

   ```yaml
   url: "https://YOUR-USERNAME.github.io"
   baseurl: ""
   ```

3. Put the **contents of web_by_academic** at the repository root, including `.github` and `.gitignore`. The root must contain Gemfile, `_config.yml`, and index.md. Do not place another web_by_academic folder around them. Do not copy materials_reference or the outer workspace.
4. Push the source to the `main` branch. GitHub Desktop is a convenient option; make the site folder your repository and publish it to your own account. If using Git commands, verify your own repository remote before pushing.
5. On GitHub, open Settings → Pages → Build and deployment → Source, and select **GitHub Actions**. This custom build is needed for Jekyll Scholar. Do not select a branch-based Jekyll build.
6. Open Actions → Build and deploy academic website. If the first push ran before Pages was enabled, use Run workflow to rerun it. The build uploads `_site` and the deploy job publishes it.
7. Once the workflow succeeds, use Settings → Pages → Visit site. Check all pages and assets on the live address.

You do not need a CNAME file or a purchased domain. This package has not been uploaded or deployed on your behalf. Your username and public text still need to be supplied.

For a project site instead, set `url` to `https://YOUR-USERNAME.github.io` and `baseurl` to `/REPOSITORY-NAME`. Templates already use `relative_url`. The workflow assumes its own source is at the repository root; if you intentionally keep a nested source folder, adjust the Ruby working directory, build command, and artifact path together.

Official publishing references:
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages

## 4. Write and update content

Edit index.md for Home and `_pages/*.md` for the other pages. The YAML block between the first two `---` lines is page configuration; text below it is page content. Preserve indentation and quote strings containing colons. Use spaces, not tabs.

Guidance appears in `<p class="editor-note">…</p>`. Replace the whole element with your text. Ordinary Markdown is easiest:

```markdown
## Section heading

Your paragraph goes here.

- First item
- Second item

[Research page]({{ '/research/' | relative_url }})
[External profile](https://example.org)
```

In Markdown links to local pages or downloads, use `relative_url` as shown. It keeps links correct if you later use a project-site path. Raw `/assets/...` links do not account for a baseurl.

Identity, role, affiliation, public email, and CV path are shared settings in `_config.yml`. Your reference documents are private drafting inputs; choose which information to make public rather than copying them into the site. The contact link and CV download appear only when their settings contain a path/address.

## 5. Publications and selected papers

Put BibTeX entries in `_bibliography/papers.bib`, exported from your citation manager or verified against your CV. A commented example lives in `_bibliography/example.bib.txt`; it is not a publication. Give every entry a unique key and use valid BibTeX braces. The main list is grouped by year, newest first.

```bibtex
@article{your_unique_key,
  author = {Yang, Bowen and Smith, Alex},
  title = {Your exact verified title},
  journal = {Your journal},
  year = {2026},
  selected = {true},
  highlight = {One sentence describing your contribution}
}
```

Replace example metadata before using it. `selected = {true}` makes the entry appear in the Home selected-publications block. Remove that field or use false to leave it only on Publications. Optional `doi` contains the DOI identifier without `https://doi.org/`. Optional `pdf` contains a local path such as `/assets/pdf/paper-key.pdf`. Empty DOI/PDF fields produce no links. Upload PDFs only when you have a public version suitable for sharing.

The bibliography renderer is `_layouts/bib.html`. Change citation style in `_config.yml` under `scholar.style`; it starts with `ieee`. Editing `.bib` content does not require layout edits.

## 6. News

Replace the initial `[]` in `_data/news.yml` with a list:

```yaml
- date: "2026-10-09"
  text: "Your actual announcement."
  url: "/publications/"
```

Dates must be quoted ISO dates. Entries sort newest first. Home shows the latest three; News shows all. Omit `url` for announcements without a link. Text is plain text, deliberately escaped rather than interpreted as HTML. Change the home limit in `_includes/home/news.html`.

## 7. Reorder, move, add, or remove sections

**Navigation order:** move entries up/down in `_data/navigation.yml`. To hide a navigation item, remove its two-line entry. This does not delete its page or make its URL private. To remove a page entirely, remove its source file too.

**Home order:** change the list in index.md:

```yaml
sections: [news, research, selected_papers]
```

This example moves News first and hides the Openings block. The supported names are `research`, `selected_papers`, `news`, and `openings`. The introduction and portrait stay at the top; to move those, edit `_layouts/about.html`. The blocks themselves live in `_includes/home/`.

**Other pages:** cut the heading and everything beneath it through the next heading, then paste the complete block where you want it. Move the figure include with its related content. The optional figure settings stay in front matter and do not need to move.

**New page:** create `_pages/service.md`:

```markdown
---
title: Service
permalink: /service/
---
## Professional service

Your text here.
```

Then add `title: Service` and `url: /service/` as an entry in navigation. **New home section:** create `_includes/home/service.html`, add a `when 'service'` include branch to the case statement in `_layouts/about.html`, then add `service` to index.md’s sections list.

## 8. Add, remove, resize, and reposition figures

Store images in assets/img with simple names such as `portrait.jpg` or `converter-platform.webp`. Compress photos before upload; approximately 1200–1600 pixels wide usually suffices for a full-width image. No automatic image conversion is installed.

For the Home portrait, edit index.md:

```yaml
profile:
  enabled: true
  image: "/assets/img/portrait.jpg"
  alt: "Portrait of Bowen Yang"
  caption: ""
  align: right
  width: 220px
```

Set enabled to false to remove the portrait and reclaim the text space. Change align to left to move it left. Change width to `180px` or `260px` to resize it. On narrow screens, the portrait automatically centers above the text.

Research and Projects each have a named figure setting in their front matter. Set enabled to false to remove a figure, set path to your image’s local path to replace its box, and change width to `60%`, `100%`, or `500px`. The width is capped at the available space. Alt text should explain the image’s content; captions should explain its relevance.

To add another figure anywhere in a Markdown page:

```liquid
{% include figure.html enabled=true path='/assets/img/your-image.jpg' alt='Describe the image' caption='Your caption' width='70%' %}
```

Move this include line above or below a paragraph to reposition it. Remove the line or change enabled to false to hide it. A missing/empty path produces a placeholder only when enabled is true. Figure appearance is shared in `_includes/figure.html` and the `.figure` rules in CSS.

## 9. Change page width, type, spacing, and colors

Edit assets/css/main.css. Its first rule exposes the main settings:

```css
:root {
  --accent: #8b255d;
  --text: #25272c;
  --muted: #656b73;
  --border: #e4e5e8;
  --max-width: 1040px;
  --body-size: 17px;
}
```

Change accent for links and active navigation. Change max-width for the entire content column. Change body-size for paragraph text. Heading sizes are in h1/h2/h3 rules. Section spacing is controlled by `.home-section`, heading margins, and `main.container`. Research-interest boxes use `.topic-grid`; change its grid-template-columns to `1fr` for one column on desktop.

Mobile rules at the end apply below 600px. Keep figure width caps and navigation wrapping to avoid horizontal overflow. System fonts keep loading fast and avoid external font requests. Test contrast after changing colors.

The shared header and footer live in `_layouts/default.html`; ordinary page titles live in `_layouts/page.html`; Home uses `_layouts/about.html`. CSS changes appearance, while these templates change page structure.

## 10. Routine maintenance

For each update: edit source → preview → check links and a narrow screen → build → commit → push → check the GitHub Actions result. Prefer short descriptive commits such as “Add October conference talk.” Update the CV PDF and webpage together when your role changes. Review Openings whenever recruiting status changes.

Keep backups in your own Git repository. To undo a bad published change, revert its commit using GitHub Desktop or GitHub’s revert workflow and push the revert. Avoid rewriting shared history. Your previous source versions remain available in Git.

Dependencies are pinned in Gemfile/Gemfile.lock. Do not update them with every content edit. Periodically review upstream security and compatibility updates; update deliberately, run the build, inspect the site, and commit the lockfile. For a chosen update, change the pinned version in Gemfile and run `bundle update jekyll` or `bundle update jekyll-scholar` as appropriate. Recheck the deployment workflow’s Ruby version if you change Ruby locally. This reduced adaptation does not receive upstream theme files automatically.

## 11. Troubleshooting

| Symptom | Check |
| --- | --- |
| Unknown bibliography tag | Use bundle exec; install dependencies; retain jekyll/scholar in plugins |
| YAML parse error | Check spaces, list indentation, closing quotes, and front-matter delimiters |
| A figure box remains | Add a real image path or set enabled to false |
| Image/PDF missing on GitHub | Check file was committed and exact capitalization matches; Linux paths are case-sensitive |
| Config changes do not appear | Restart local Jekyll |
| Live CSS or links broken | Check url/baseurl and repository-root upload layout |
| Deployment fails | Open the first failed Actions step; verify Pages source is GitHub Actions |
| Linux gem platform missing | Run `bundle lock --add-platform x86_64-linux`, commit Gemfile.lock, then rerun |
| A removed navigation page is still reachable | Remove the page source, not just its navigation entry |
| Publications are empty | Add real entries to papers.bib; comments are not records |
| Selected paper absent | Use selected = {true}, matching the Home query |

GitHub deployment cannot be verified until your own repository and Pages settings exist. The included workflow builds pull requests without deployment and deploys main-branch pushes or manual runs.
