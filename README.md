# TheoriginalMMM.github.io

Academic and professional portfolio built with Jekyll and the Minimal Mistakes theme.

## Important: keep the Jekyll structure

The source of the website is:

```text
_config.yml
index.md
_data/navigation.yml
_pages/
_projects/
_sass/
assets/css/main.scss
assets/images/
assets/documents/
```

Do not commit the generated `_site/` folder. Do not add `.nojekyll`: that file disables the GitHub Pages Jekyll build. Do not place a competing `index.html` beside `index.md`.

## Repair the current clone in VS Code

Start from the root of the clone already opened in VS Code.

### 1. Preserve the current work on a safety branch

```bash
git switch -c fix-jekyll-portfolio
git status
```

Your current modifications follow the new branch automatically. Do not run
`git pull`, `git restore`, `git reset` or `git clean` before saving this work.

### 2. Remove only generated or conflicting files

The following paths were created by the incompatible static-site version and must not remain in the Jekyll source:

```bash
rm -rf _site .bundle vendor
rm -f .nojekyll index.html
rm -f assets/css/styles.css assets/js/main.js
rm -f _plugins/ssl_fix.rb Gemfile.lock
```

These commands target only Jekyll output, local Bundler state and the conflicting static files. They do not remove `.git`, `_pages`, `_projects`, `_data` or your source history.

### 3. Copy the corrected Jekyll source

Extract `Portfolio_Jekyll_Corrected_TheoriginalMMM_v10.zip` outside the
repository. The archive already contains the site files at its root. Copy all
of its contents into the repository root and accept replacement for files with
the same names.

After copying, verify:

```bash
test -f _config.yml
test -f index.md
test -f _pages/projets.md
test -f _projects/wireless_channel_charting.md
test -f assets/css/main.scss
test ! -e .nojekyll
test ! -e index.html
```

### 4. Preview locally

Keep using the working Ruby 3.2.2 managed by `rbenv`; do not mix it with the
Homebrew Ruby 4 installation. Verify the active interpreter:

```bash
ruby -v
which ruby
```

The expected results are Ruby `3.2.2` and a path under `~/.rbenv/`. The first
error came from `jekyll-remote-theme` contacting GitHub during the build. The
second (`undefined method tainted?`) came from the outdated combination
`github-pages 222` / `Liquid 4.0.3`. This version installs the theme locally and
pins `github-pages 232`, which uses Jekyll 3.10 and Liquid 4.0.4.

Then, from the repository root:

```bash
bundle config set --local path vendor/bundle
rm -f Gemfile.lock
bundle install
bundle exec jekyll clean
bundle exec jekyll serve --livereload
```

Open `http://127.0.0.1:4000`. Check the menu, every page under `_pages`, every project, the portrait and both CV downloads.

### 5. Commit and publish

```bash
git status
git add -A
git commit -m "Restore Jekyll portfolio structure and update content"
git push -u origin fix-jekyll-portfolio
```

Create a pull request into `main`. The included workflow validates the site
without publishing it. Merge only after the `Jekyll build and deploy` check
succeeds.

In **Settings > Pages**, set **Source** to **GitHub Actions**. The workflow
publishes only commits pushed to `main`; pull requests are checked without
deployment.

The public address is `https://theoriginalmmm.github.io/`.

## Included portfolio content

The project collection includes doctoral wireless-AI research, wind-power
forecasting, medical imaging, unsupervised learning, reinforcement learning,
smart environments, multi-agent systems, generative imaging and adaptive
routing. Project cards use repository-owned SVG illustrations and selected
original screenshots, so the website has no external image dependency for its
visual presentation.

The portfolio also includes a Talks & Teaching page with downloadable MOCSID
and CITI/3GE presentations, plus an Activities & Engagement page covering
community involvement, travel and outdoor interests.

Experience and education cards use local institution logos and valid HTML
lists. The experience timeline also includes the 2020 FFSE Auvergne-Rhône-Alpes
internship. Selected projects use the supplied project-specific illustrations.

## Common checks

If a build fails, open **Actions > Jekyll build and deploy** and inspect the
failed step. Do not add an SSL-bypass plugin and never disable certificate
verification.

Before printing the CV, open the deployed site and scan its QR code from a phone.

