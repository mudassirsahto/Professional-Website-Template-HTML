# Professional Static Website Template (HTML) 
<img width="2664" height="1464" alt="Webtemplate" src="https://github.com/user-attachments/assets/41fcf663-9e61-4500-bb97-032f1405ddf0" />

This project is a simple static website deployed using GitHub Actions with a full CI/CD pipeline.
Every time I push code to the main branch, GitHub Actions automatically:

Checks out the latest code

Runs HTML linting (using HTMLHint)

Deploys the website to GitHub Pages

📂 Project Structure
my-website/
│
├── index.html         # Main website file
├── .github/
│   └── workflows/
│       └── deploy.yml # CI/CD workflow definition
└── README.md          #

⚙️ CI/CD Workflow (GitHub Actions)

The workflow is defined in .github/workflows/deploy.yml.
It runs on every push to the main branch:

name: Deploy Website

on:
  push:
    branches:
      - main

jobs:
  build-deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: Install dependencies
        run: npm install -g htmlhint

      - name: Run Linter
        run: htmlhint "**/*.html" || true

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./

🛠️ How It Works

Clone this repo

git clone https://github.com/YOUR_USERNAME/my-website.git
cd my-website


Make changes to index.html (or add new HTML/CSS/JS files).

Push your changes:

git add .
git commit -m "Update website"
git push origin main


GitHub Actions will automatically build & deploy your site.

✅ Features

Automated CI/CD pipeline

Linting to keep HTML clean

GitHub Pages deployment (free hosting)

📜 License

This project is licensed under the MIT License.

This is a source for a static website template which has been downloaded and configured with a contact us page. This template further consists of input text fields, labels, message box and a submit button down below.

This is a template which has been sourced and referenced from W3.css.
