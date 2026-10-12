# al-folio attribution and adaptation

Source: https://github.com/alshedivat/al-folio

The `_layouts/about.html` structure adapts the classic al-folio v0.14.0 about layout:
https://github.com/alshedivat/al-folio/blob/v0.14.0/_layouts/about.liquid

Retained concepts include the post/header/article structure, optional left/right portrait, clearing text around the portrait, and separate selected-paper/news sections. Removed features include image transformations, blog posts, social icons, newsletters, JavaScript widgets, and Bootstrap classes. Section order is now a configurable list; figures use a small local include. The rest of the site uses purpose-written minimal layouts and CSS with the classic al-folio academic presentation as its design reference.

Upstream al-folio currently uses a v1 plugin architecture; this package deliberately does not depend on that runtime. Do not assume upstream al-folio configuration options or tutorials will work without adaptation. Review upstream changes manually rather than merging its whole repository. The accompanying LICENSE preserves its MIT notice.

Jekyll and Jekyll Scholar are installed as Ruby gems, with their own upstream licenses. This package does not vendor their source.
