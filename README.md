# Anderson Lab Website

This repository contains the MkDocs-based source for the Anderson Lab website at UC Berkeley.

🌐 Live site: [https://ucb-bioe-anderson-lab.github.io/](https://ucb-bioe-anderson-lab.github.io/)

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/UCB-BioE-Anderson-Lab/UCB-BioE-Anderson-Lab.github.io.git
cd UCB-BioE-Anderson-Lab.github.io
```

### 2. Set Up the Environment

Use the provided setup script:

```bash
./setup.sh
```

This will:
- Create a virtual environment in `mkdocs-env/`
- Inject required environment variables
- Install dependencies from `requirements.txt`

### 3. Activate Environment

```bash
source mkdocs-env/bin/activate
```

---

## 🛠 Serving the Site Locally

To view the site during development:

```bash
python main.py serve
```

Visit [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

---

## 📦 Building the Site

To generate the static files:

```bash
python main.py build
```

The output will appear in the `site/` directory.

---

## 🚀 Deploying to GitHub Pages

To publish the site:

```bash
python main.py deploy
```

This uses `mkdocs gh-deploy` to push the built site to the `gh-pages` branch.

---

## 📁 Structure Overview

```plaintext
docs/               # Site content (Markdown, assets)
mkdocs.yml          # Site configuration
main.py             # Workflow script (serve, build, deploy)
setup.sh            # Environment setup script
requirements.txt    # Python dependencies
```

---

## 🧠 Notes

- All publication and patent metadata is in `docs/data/`
- Dynamic content is rendered using inline JavaScript
