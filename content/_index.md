---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: '0rem'

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: me
      text: ''
      show_education: false
      # Show a call-to-action button under your biography? (optional)
      button:
        text:
        url:
      headings:
        about: 'Professional Summary'
        education: ''
        interests: ''
        ongoing: "What I'm Working On"
    design:
      # Use the new Gradient Mesh which automatically adapts to the selected theme colors
      background:
        gradient_mesh:
          enable: true

      # Name heading sizing to accommodate long or short names
      name:
        size: md # Options: xs, sm, md, lg (default), xl

      # Avatar customization
      avatar:
        size: medium # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: rounded # Options: circle (default), square, rounded

  - block: markdown
    content:
      title: ''
      text: |
        {{< bio_grid >}}
          {{< display_list key="certifications" type="featured" header="🎓 Core Certifications" >}}
          {{< display_list key="awards" type="featured" header="🏆 Notable Awards" >}}
        {{< /bio_grid >}}
    design:
      columns: 2
      css_class: "wide-block"
---
