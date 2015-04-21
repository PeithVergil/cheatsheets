MkDocs
======


Installation
--------------------------------------------------

```bash
pip install mkdocs
```


Usage
--------------------------------------------------

Start a new project:

```bash
mkdocs new [myproject]
```

Use the built-in server to serve the static pages during development:

```bash
mkdocs serve
```

To add pages, just create Markdown files inside the `docs/` directory. Then, edit the `mkdocs.yml` file and add the new pages to the list:

```yaml
site_name: My Project
pages:
-["index.md", "Home"]
-["page1.md", "Page1"]
-["page2.md", "Page2"]
-["about.md", "About"]
```

Build the site:

```bash
mkdocs build
```