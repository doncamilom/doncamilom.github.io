# AGENTS.md

## Cursor Cloud specific instructions

This is a Jekyll 3.8.5 static blog site using the `github-pages` gem (v203) with the Minima theme.

### Ruby environment

- Ruby 2.7.8 is required (managed via `rbenv`). The Gemfile.lock pins gem versions that are incompatible with Ruby 3.x.
- rbenv is installed at `~/.rbenv` and must be initialized with `eval "$(rbenv init -)"` in each shell session before running Ruby/Bundler commands.
- OpenSSL 1.1.1w is installed at `/opt/openssl-1.1` (required by Ruby 2.7 since Ubuntu 24.04 ships OpenSSL 3.x).
- Nokogiri 1.10.7 requires a source patch to compile on Ubuntu 24.04 (glibc 2.39 `canonicalize` symbol conflict). The patched version is pre-installed globally in the rbenv Ruby 2.7.8 gems.

### Running the dev server

```
eval "$(rbenv init -)"
bundle exec jekyll serve --host 0.0.0.0 --port 4000
```

Site will be available at `http://localhost:4000`.

### Building the site

```
eval "$(rbenv init -)"
bundle exec jekyll build
```

Output goes to `_site/`.

### Key caveats

- There are no automated tests in this repository. Validation is done by building the site and checking that pages render.
- The `jekyll-github-metadata` plugin may emit warnings without a `JEKYLL_GITHUB_TOKEN` env var; the site still builds fine without it.
- Ruby 2.7 deprecation warnings about keyword arguments are expected and harmless with Jekyll 3.8.5.
- Gems are installed globally in the rbenv Ruby (not in `vendor/bundle`) because nokogiri 1.10.7 cannot be compiled fresh via `bundle install --path` on this system.
