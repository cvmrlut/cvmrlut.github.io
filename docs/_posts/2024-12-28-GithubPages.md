# Build github pages using the remote theme & Markdown
[github-pages](https://github.com/skills/github-pages) |
[Jekyll Themes](http://jekyllthemes.org)

## E.G. [sighingnow/jekyll-gitbook](https://github.com/sighingnow/jekyll-gitbook)
/_config.yml
```
remote_theme: sighingnow/jekyll-gitbook
plugins:
  - jekyll-feed
  - jekyll-readme-index
  - jemoji
  - jekyll-remote-theme
```
/Gemfile
```
source "https://rubygems.org"
git_source(:github) { |repo_name| "https://github.com/#{repo_name}" }
gem "jekyll"
gem 'jekyll-feed'
gem 'jekyll-readme-index'
gem 'jemoji'
gem 'webrick'
gem 'jekyll-remote-theme'
```
.github/workflows/jekyll.yml
```
name: Deploy GitHub Pages

on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v4
      - uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      - id: deployment
        uses: actions/deploy-pages@v4
```
.github/workflows/jekyll.yml Minimum code
```
name: Deploy GitHub Pages
on:
  push:
    branches: ["main"]
  workflow_dispatch:
permissions:
  pages: write
  id-token: write
jobs:
  deploy:
    environment:
      name: github-pages
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      - uses: actions/deploy-pages@v4
```
Create `_posts` folder and add Markdown file.

# More themes
## [cotes2020/jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)
[Tech](https://zhang-nianqiang.github.io/posts/Deploy-Jekyll-on-GitHub-Pages-using-Chirpy-Theme/)


## [just-the-docs](https://github.com/just-the-docs/just-the-docs)

## [Fast.ai](https://github.com/fastai/fastpages)
https://github.com/fastai/fast_template/generate |
https://www.fast.ai/2020/01/16/fast_template

## [Academic Pages](https://github.com/academicpages/academicpages.github.io)


<div align='center'><details><summary>

# Special Usage
</summary>

# Merge table
<table border="0">
   <tr>
      <td rowspan="2">KVM</td>
      <td>Container & Services</td>
   </tr>
   <tr>
      <td align="center" >OpenStack</td>
   </tr>
   <tr>
      <td>PRoot</td>
      <td align="center" >LXC</td>
   </tr>
   <tr>
      <td align="center" colspan="2">Hardware</td>
   </tr>
</table>

# Mermaid flowcharts
```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```
<br></details></div>