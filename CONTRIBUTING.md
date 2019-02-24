# Contrib

- [Contrib](#contrib)
  - [Content](#content)
    - [Adding a new Language](#adding-a-new-language)
    - [Adding and Modifying segments to a Language](#adding-and-modifying-segments-to-a-language)
  - [HTML and Design](#html-and-design)

## Content
### Adding a new Language

In `_config.yml` we need to create a new `collection` for the Language
```yaml
collections:
  NewLanguage: # This is the part we need to add
    output: true # Note that output must be set to true
    icon: https://google.ca/someImageUrl.png # image that will appear on the main screen
```

Create a new **folder** under the `_collections` folder with the following naming scheme
```
_NewLanguage
```
- The name of the language must be the same as the one added into `_config.yml`

Create a new **page** under the `sheets` folder with the following name scheme
```
NewLanguage.md
```

and with the contents of 
```frontmatter
---
layout: languageSheet
title: CPP
---
```

Now the page will be automatically generated at `/sheets/NewLanguage.html`

---

### Adding and Modifying segments to a Language
Segments, or blocks that can be found on a language page at `/sheets/Language.html` live in the `_collections/_Language` folder.

Modifying an existing segment will update the Language page.

To add a new segment, create a new file at `_collections/_Language/Segment.md` with the contents
```markdown
---
title: Print Statements
description: Display text on the console
langauge: CPP
# Display name is optional, and will be displayed instead of language
displayname: C++
---

# All content can be shown below, content is written in markdown format
Content
```

---

## HTML and Design
- Front page `/` can be styled at `/index.html`. It also uses the `/css/main.css` and `/js/script.js` files.
  - In addition, part of the index page also lives at `/_layouts/index.html`
- Individual language pages can be styled at `/_layouts/languageSheet.html`
  - Syntax highlighting can be modified at `/css/monokai.css`
- CSS files can be added into the `/css` folder and then added into any **HTML file** using the normal
    ```html
    <link rel="stylesheet" type="text/css" href="/css/styles.css">
    ```
- JS files can be added into the `/js` folder and added normally into any **HTML** file using the normal
    ```js
    <script src="/js/someScript.js"></script>
    ```