# Documentation

Accompanying documentation is vital to ensure the maintainability of a codebase, irrespective of whom is working on it. The main purpose of the documentation is to describe ***why*** the code does what it does, and is an important part of the development process. The documentation should be sufficient to allow others to repeat the analysis. Documentation can aid in knowledge transfer, support in debugging of issues, revisiting your code in the future, to allow others to use your code easily and build upon it, and allow reproducibility and transparency.

1. Documentation should be **simple** and **concise**.
2. Documentation should be kept **up-to-date**. As code is updated, the associated documentation should be updated. You should trim your documentation as appropriate, removing anything outdated.

## Creating documentation

Markdown-based systems are one of the most popular documentation systems. Markdown is a lightweight markup language for creating formatted text using a plain-text editor. Markdown (specifically GitHub Flavored Markdown, GFM) is used across GitHub (e.g. README.md files), and is easy to pickup. A key benefit to using Markdown as opposed to Word for example, is that version control solutions can easily track any changes.

Mermaid is a Javascript-based diagramming and charting tool, which uses Markdown-inspired text definitions and a renderer to create and modify complex diagrams. These charts are created entirely using text through a simple syntax. Mermaid supports many different types of diagrams, including flowcharts; sequence, class, state and entity relationship diagrams, Gantt, and pie charts. These diagrams can also be generated through code. You can find substantial documentation [on their website](https://mermaid-js.github.io/mermaid/#/).

Visual Studio Code supports the creation of Markdown and Mermaid graphs (with export functionality) through extensions available in the marketplace. You can also use [StackEdit](https://stackedit.io) as a free solution to write Markdown and Mermaid which can be synced using Google Drive or Dropbox. [Mermaid Live](https://mermaid.live) is a free site that lets you render Mermaid graphs, which can be downloaded in the PNG or SVG image format.

## Markdown (GFM)

This is not intended to be a comprehensive documentation of Markdown, however some basic elements are presented below.

---

### Text

Text is rendered as follows:

```markdown
This is some text.

This is more text.
```

Which renders as follows:

This is some text.

This is more text.

---

### Headings

Headings are created using the `#` symbol. Multiple consecutive `#` are used to create ever smaller headings.

```markdown
### heading 1

This is some text.

#### heading 2

This is some more text.

##### heading 3

This is even more text.
```

#### heading 1

This is some text.

##### heading 2

This is some more text.

###### heading 3

This is even more text.

---

### Lists

Lists can be ordered or unordered, where ordered lists are ordered automatically. Lists can also have sub-items, which can be a mix of ordered or unordered lists. Use four spaces or one tab to create an sub-list.

```markdown
* item 1
* item 2
* item 3
    * item 3.1

1. item 4
1. item 5
1. item 6
    - item 6.1
```

* item 1
* item 2
* item 3
    * item 3.1

1. item 4
1. item 5
1. item 6
    - item 6.1

--- 

### Tables

Tables can be created using GitHub Flavoured Markdown (GFM). Columns can be left, center or right aligned, using `:---`, `:---:` or `---:` respectively (see line 2 below).  

```
| column 1 | column 2 | column 3 |
| :--- | :---: | ---: |
| left align | center align | right align |
| **bold** | _italics_ | ***bold italic*** |
| `code` |
```

| column 1 | column 2 | column 3 |
| :--- | :---: | ---: |
| left align | center align | right align |
| **bold** | _italics_ | ***bold italic*** |
| `code` |

## Mermaid

