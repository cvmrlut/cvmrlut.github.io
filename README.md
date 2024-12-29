# 简洁快速使用Jekyll搭建Github Pages
[官方教程](https://github.com/skills/github-pages)

## E.G. [sighingnow/jekyll-gitbook](https://github.com/sighingnow/jekyll-gitbook)

>从项目的`_config.yml`&`Gemfile`复制信息
_config.yml
```
remote_theme: sighingnow/jekyll-gitbook
plugins:
  - jekyll-feed
  - jekyll-readme-index
  - jemoji
  - jekyll-remote-theme
```
Gemfile
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
Create `_posts` folder and add Markdown file.

## [cotes2020/jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)
[Tech](https://zhang-nianqiang.github.io/posts/Deploy-Jekyll-on-GitHub-Pages-using-Chirpy-Theme/)
