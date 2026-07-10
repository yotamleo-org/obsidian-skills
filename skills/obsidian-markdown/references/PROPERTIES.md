# Properties (Frontmatter) Reference

Properties use YAML frontmatter at the start of a note:

```yaml
---
title: My Note Title
date: 2024-01-15
tags:
  - project
  - important
aliases:
  - My Note
  - Alternative Name
cssclasses:
  - custom-class
status: in-progress
rating: 4.5
completed: false
due: 2024-02-01T14:30:00
---
```

## Property Types

| Type | Example |
|------|---------|
| Text | `title: My Title` |
| Number | `rating: 4.5` |
| Checkbox | `completed: true` |
| Date | `date: 2024-01-15` |
| Date & Time | `due: 2024-01-15T14:30:00` |
| List | `tags: [one, two]` or YAML list |
| Links | `related: "[[Other Note]]"` |

### Lists of Wikilinks

When defining list properties that contain multiple wikilinks in frontmatter, use the multi-line YAML array syntax. This is the format Obsidian generates by default when adding multiple values via the Properties UI.

```yaml
---
related_to:
  - "[[Note 1]]"
  - "[[Note 2]]"
  - "[[Note 3]]"
---
```

Wikilinks **must be wrapped in quotation marks** to ensure valid YAML parsing.

While inline arrays such as `related_to: ["[[Note 1]]", "[[Note 2]]"]` are valid YAML, they are **not the format Obsidian uses or expects** when managing properties through its interface.

## Default Properties

- `tags` - Note tags (searchable, shown in graph view)
- `aliases` - Alternative names for the note (used in link suggestions)
- `cssclasses` - CSS classes applied to the note in reading/editing view

## Tags

```markdown
#tag
#nested/tag
#tag-with-dashes
#tag_with_underscores
```

Tags can contain: letters (any language), numbers, underscores `_`, hyphens `-`, forward slashes `/` (for nesting). A tag must include at least one non-numerical character (`#1984` is invalid, `#1984book` is valid).

In frontmatter:

```yaml
---
tags:
  - tag1
  - nested/tag2
---
```
