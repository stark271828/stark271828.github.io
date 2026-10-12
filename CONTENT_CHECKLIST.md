# Content checklist before launch

- [ ] Confirm your name, position, and affiliation in `_config.yml`.
- [ ] Set `url` to your GitHub Pages address. Keep `baseurl` empty for your account website.
- [ ] Add your public email and optional CV PDF. Export a public version of the CV yourself.
- [ ] Write the Home introduction and replace both guidance paragraphs.
- [ ] Add a portrait with descriptive alt text, or set `profile.enabled: false`.
- [ ] Populate the research overview, four topic sections, and future directions.
- [ ] Add research/project images and accurate captions, or set each figure’s `enabled: false`.
- [ ] Add verified BibTeX entries and mark a few papers selected. Remove publication guidance when finished.
- [ ] Add project descriptions with your role, collaborators, status, and public results.
- [ ] Add people information, or temporarily remove People from navigation.
- [ ] Add teaching experience with exact roles, philosophy, and mentoring examples.
- [ ] Add news, or hide its home block until there are announcements.
- [ ] State accurate recruiting status, or hide Openings from navigation and Home until needed.
- [ ] Replace Contact guidance with real public links and concise background.
- [ ] Find all remaining guidance: `rg -n 'editor-note|Optional|Replace' index.md _pages _includes`.
- [ ] Remove entire `<p class="editor-note">…</p>` elements and write ordinary Markdown. Do not merely hide them with CSS.
- [ ] Test every navigation item, image, DOI, PDF, and email link; check phone-width layout.
- [ ] Run a final production build and review `_site`. Commit source changes and deploy.

The statements guide the research/teaching prompts; the CV guides the appointment, platforms, and experience prompts. No funding availability or faculty appointment is asserted in the placeholders.
