# Seldon He's Portfolio

[![Deploy site](https://github.com/seldonhe/seldonhe.github.io/actions/workflows/deploy.yml/badge.svg)](https://github.com/seldonhe/seldonhe.github.io/actions/workflows/deploy.yml)
[![Check links](https://github.com/seldonhe/seldonhe.github.io/actions/workflows/broken-links.yml/badge.svg)](https://github.com/seldonhe/seldonhe.github.io/actions/workflows/broken-links.yml)

Personal portfolio for Seldon He, a Vancouver-based business and data analytics professional focused on financial planning, risk management, visualization, forecasting, and decision support.

**Live site:** [seldonhe.github.io](https://seldonhe.github.io/)

## Highlights

- Professional profile and technical skills
- Selected analytics and strategy projects
- Resume and contact information
- Automated GitHub Pages deployment and link validation

## Local Development

Requirements: Ruby 3.2+, Bundler, Python 3, Jupyter, ImageMagick, and Node.js.

```bash
bundle install
pip install jupyter
bundle exec jekyll serve
```

Open `http://localhost:4000` after the server starts.

## Deployment

Pushing to `main` builds and publishes the site through GitHub Actions. Pull requests build the site without deploying it.

## Credits

Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme. Theme code remains available under its original [MIT license](LICENSE).
