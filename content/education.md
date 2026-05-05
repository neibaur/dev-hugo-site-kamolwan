---
title: 'Education'
date: 2023-10-24
type: landing

design:
  spacing: '2rem'

# Note: `username` refers to the user's folder name in `content/authors/`

# Page sections
sections:
  - block: markdown
    content:
      title: 🎓 Certifications
      text: |
        {{< display_list key="certifications" type="all" header="" >}}
  - block: education
    content:
      username: me
    design:
      date_format: 'January 2006'
  - block: resume-languages
    content:
      title: Languages
      username: me
---
