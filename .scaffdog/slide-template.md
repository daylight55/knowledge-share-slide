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

# `{{ inputs.category == "tips" || "!" }}slides/tips/{{ inputs.title }}.md`

```markdown
---
marp: true
theme: {{ inputs.theme }}
paginate: true
---

# {{ inputs.title }}

```

# `{{ inputs.category == "introduction" || "!" }}slides/introduction/{{ inputs.title }}.md`

```markdown
---
marp: true
theme: {{ inputs.theme }}
paginate: true
---

# {{ inputs.title }}

```

# `{{ inputs.category == "culture" || "!" }}slides/culture/{{ inputs.title }}.md`

```markdown
---
marp: true
theme: {{ inputs.theme }}
paginate: true
---

# {{ inputs.title }}

```
