---
name: 'slide-template'
root: '.'
output: slides/*'
ignore: []
questions:
  category:
    message: 'Choose your slide category.'
    choices:
      - 'tips'         # 困ったこと・対処法
      - 'introduction' # 技術紹介・入門
      - 'culture'      # 文化取り組み
    initial: tips
  title: 'Enter your slide title.'
  theme:
    message: 'Choose the slide theme.'
    choices:
      - 'gaia'
    initial: gaia

---

# `slides/{{ inputs.category }}/{{ inputs.title }}.md`

```
{{ if inputs.category == "tips" }}
  {{ 'slide-templates/tips.md' | read }}
{{ else if inputs.category == "introduction" }}
  {{ 'slide-templates/introduction.md' | read }}
{{ else if inputs.category == "culture" }}
  {{ 'slide-templates/culture.md' | read }}
{{ end }}
```
