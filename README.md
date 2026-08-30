# bakshisoham.github.io

Source for my academic homepage, <https://bakshisoham.github.io> — a Jekyll 4
site built and deployed by GitHub Actions (`.github/workflows/pages.yml`).

## Layout

| Content | File |
|---|---|
| Papers, preprints, talks | `menu/research.md` |
| Courses taught | `menu/teaching.md` |
| Blog posts (হ য ব র ল) | `_posts/YYYY-MM-DD-Title.md` |
| Menu items, social links | `_data/settings.yml` |
| Slides, CV, other PDFs | `assets/file/` |
| Latin Modern webfonts | `assets/fonts/` |

## Preview locally

```
bundle install
bundle exec jekyll serve --config _config.yml,_config.local.yml --livereload
```

`_config.local.yml` is gitignored; it overrides `url` and `site.github.url` to
`http://localhost:4000` so stylesheets and links resolve while previewing.

## Credits

The site began life as a fork of [Lagrange](https://github.com/LeNPaul/Lagrange)
by Paul Le. No Lagrange code remains — the layouts, includes and stylesheets
have since been rewritten.

Typeset in [Latin Modern](https://www.gust.org.pl/projects/e-foundry/latin-modern)
(GUST, GFL), with [Noto Serif Bengali](https://fonts.google.com/noto/specimen/Noto+Serif+Bengali)
for Bengali text. Mathematics is rendered with MathJax 3.
