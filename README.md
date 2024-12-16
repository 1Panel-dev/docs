This repository contains the [official documentation](https://docs.1panel.hk) for the [1Panel project](https://github.com/1Panel-dev/1Panel). The documentation is built using the [MkDocs](https://github.com/mkdocs/mkdocs) framework with the [Material for MkDocs](https://github.com/squidfunk/mkdocs-material) theme.

## Local Development

### Clone the Repository

```bash
git clone https://github.com/1Panel-dev/docs.git
```

### Install Dependencies

```bash
cd docs
pip install -r requirements/requirements.txt
```

### Modify documentation content

The structure of the documentation is defined in the `mkdocs.yml` file, and the actual content is located in the docs directory.

The documentation content is written in Markdown syntax. To add new documentation, you need to update the nav section in the `mkdocs.yml` file to include the corresponding navigation for the new section.

### Debug documentation locally

```bash
mkdocs serve
```

After running the above command, you can view the generated documentation at `http://127.0.0.1:8000` . The page content will automatically update when changes are made to the documentation.

### Build Documentation

```bash
mkdocs build
```

After running the above command, static files for the documentation site will be generated in the site directory. You can deploy the documentation by copying the contents of this directory to any HTTP server.

### Issue Feedback

If you find any errors in the documentation or have questions about the content, please submit a GitHub Issue to the [1Panel project’s main repository](https://github.com/1Panel-dev/1Panel/issues) .
