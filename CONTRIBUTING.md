[< Overview](README.md)

# Contributing to Documentation

Any additions to AppBuilder documentation is welcome. Here are few guidelines to keep our documentation consistent:

1. Follow the [file structure](#file-structure)
1. [Use markdown](#markdown)
1. Follow the [page format](#page-format)

## File Structure

Try to follow the existing hierarchy when adding documentation. Add a page folder under the appropriate topic. Add a Page.md file, and an images folder if needed.

```
📁topic
  📁subtopic
    📁page
      📁images
      Page.md
```

## Markdown

### Learn Markdown

- [Mastering Markdown](https://guides.github.com/features/mastering-markdown/) - Github's markdown Guide
- [Markdown Cheetsheet](https://www.markdownguide.org/cheat-sheet/) - Quick markdown reference

### Tools

- [Docs to Markdown](https://github.com/evbacher/gd2md-html/wiki) - Google drive extension to convert an existing document to Markdown
- [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) - Easy tool for creating/formatting a table into markdown

## Format

Start the file with a back link to the most applicable index/topic page.

```markdown
[< Previous Index](../Index.md)

# Title

## Heading

### Sub Heading

...

######
```

Start with a title using heading 1 (`#`). Only use this heading once for the title. Start with heading 2 (`##`) and adding one level for each nested heading. Do not skip heading levels.
