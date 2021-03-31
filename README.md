# sciencepumps.github.io

High-Entropy Science 

## Install

### With a Ruby environment

```
brew install rbenv
rbenv init # (put eval "$(rbenv init -)" in bash_profile)
rbenv install 2.4.1 # install local ruby
rbenv local 2.4.1 # switch to local version
```

### Install jekyll

```
gem install jekyll bundler
bundle install
```

### Build and serve the site locally

```
bundle exec jekyll serve
```

Specify `--drafts` to see draft posts (`_drafts`).
