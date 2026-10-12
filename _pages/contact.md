---
title: CV / Contact
permalink: /contact/
description: Professional background and contact information
---
## Curriculum vitae

{% if site.cv_pdf and site.cv_pdf != '' %}
[Download my CV (PDF)]({{ site.cv_pdf | relative_url }})
{% else %}
<p class="editor-note">Export your public CV to PDF, save it as assets/pdf/Bowen_Yang_CV.pdf, and set cv_pdf in _config.yml. The download link will appear automatically.</p>
{% endif %}

## Background

<p class="editor-note">Add a concise education and appointment summary from your CV. Optionally include selected honors and professional service, keeping the complete record in the PDF.</p>

## Contact

{% if site.email and site.email != '' %}<p>Email: <a href="mailto:{{ site.email | escape }}">{{ site.email | escape }}</a></p>{% else %}<p class="editor-note">Set email in _config.yml to display your preferred public contact address.</p>{% endif %}

<p class="editor-note">Optionally add institution profile, Google Scholar, ORCID, GitHub, and LinkedIn links. Add an office address only if you want it public.</p>
