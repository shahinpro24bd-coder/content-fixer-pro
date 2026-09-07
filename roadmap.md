# Roadmap
- [done] Fixed uneditable hero pill + all wiped content (deleted 23 empty CMS entries; hardened editor/save/apply against empty values)
- [done] Answered where historical text data lives (Lovable version history + site_content table)

- [x] Gallery nav links translate to Bangla
- [x] Removed foreign CMS content; site content namespaced per site
- [x] Text changing on its own: fixed 4 causes — shared database rows with a cloned site (new unique namespace), positional save keys (permanent data-cms-id stamped in every page), stale localStorage copy of content, and the translator re-wording saved text in English mode
