# Minimal Notes Template

> **Template repository:** [https://github.com/alexusgracia/manuals](https://github.com/alexusgracia/manuals)

[![Deploy Sphinx docs to GitHub Pages](https://github.com/<user>/<repo>/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/<user>/<repo>/actions)

This template allows you to create course notes using Sphinx, Markdown, and Read the Docs in the simplest way possible.

## Structure

- `requirements.txt`: required dependencies
- `.gitignore`: ignores automatically generated files
- `LICENSE`: content license
- `docs/`: folder with the documentation in Markdown
  - `template.md`: template for new topics
- `images/`: folder for images
  
## Which files should teachers edit?

- **docs/index.md**: This is the main index of the documentation. Here you can add the cover, introduction, and the list of topics or chapters.
- **docs/tema1.md, docs/tema2.md, ...**: Create or edit these files for each topic, chapter, or section of the course. You can add as many Markdown files as you need, linking them from the index.
- **docs/conf.py**: (Optional) Only if you want to change the project title, author, or some advanced Sphinx configuration.

The rest of the files usually do not need to be modified to create your notes.

## How to build the documentation locally

1. **Clone the repository:**

   ```bash
   git clone https://github.com/alexusgracia/manuals.git
   cd manuals
   ```

2. **Create a virtual environment (optional but recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Build the documentation:**
   You can use either of the following options:
   - Run the command directly:

     ```bash
     sphinx-build -b html docs docs/_build/html
     ```

   - Or use the provided script (on Unix/Linux/Mac):

     ```bash
     ./build.sh
     ```

     (If needed, make it executable first: `chmod +x build.sh`)
5. **View the documentation locally:**
   - Open the file `docs/_build/html/index.html` in your web browser.
   - You can usually double-click the file or right-click and choose "Open with" and select your browser.
   - Alternatively, you can enter the file path in your browser's address bar (e.g., `file:///C:/path/to/manuals/docs/_build/html/index.html` on Windows).

## Markdown Examples

### Image

```markdown
![That's me](/images/alexandre.jpg)
```

### Table

```markdown
| Concept   | Description        |
|-----------|-------------------|
| Markdown  | Simple syntax     |
| Sphinx    | Docs generator    |
```

### Code

```python
print("Hello, world!")
```

### Math equations (LaTeX)

You can write inline equations: `$E=mc^2$` or block equations:

```markdown
$$
\int_0^1 x^2 dx = \frac{1}{3}
$$
```

### Quotes and links

```markdown
> "Education is the most powerful weapon which you can use to change the world." — Nelson Mandela

[Markdown Guide](https://www.markdownguide.org/basic-syntax/)
```

## Customize the Sphinx theme

To change the appearance, edit the `html_theme` variable in `docs/conf.py`. For example:

```python
html_theme = 'alabaster'
```

See the [Sphinx themes documentation](https://www.sphinx-doc.org/en/master/usage/theming.html) for more options.

## Automatic deployment on GitHub Pages

1. Push all files to the `main` branch of your GitHub repository.
2. Go to the **Actions** tab in your repository and make sure the "Deploy Sphinx docs to GitHub Pages" workflow runs successfully.
3. Go to **Settings** > **Pages** in your repository.
4. In the **Build and deployment** section, select **GitHub Actions** as the source.
5. Once the workflow is complete, your documentation will be available at the URL provided by GitHub Pages (usually `https://<user>.github.io/<repo>/`).
