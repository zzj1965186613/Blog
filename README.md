# Blog

My personal blog built with [Jekyll](https://jekyllrb.com/) and hosted on [GitHub Pages](https://zzj1965186613.github.io/Blog).

**Theme:** [Minima](https://github.com/jekyll/minima)

---

## Live Site

[https://zzj1965186613.github.io/Blog](https://zzj1965186613.github.io/Blog)

---

## Posts

| Date | Title |
|------|-------|
| 2026-05-01 | 我的第一篇博客 |
| 2026-05-02 | Welcome to Jekyll! |
| 2026-05-03 | 我的第二篇博客 |

---

## Local Development

### Prerequisites

- Ruby (v3.0+ recommended)
- Bundler

### Setup

```bash
git clone https://github.com/zzj1965186613/Blog.git
cd Blog
bundle install
```

### Serve Locally

```bash
bundle exec jekyll serve
```

Or on Windows, run `serve.bat`.

The site will be available at `http://localhost:4000/Blog`.

### Deploy

Push to `master` branch to trigger GitHub Pages deployment, or run:

```bash
git push origin master
```

Or on Windows, run `push.bat`.

---

## Structure

```
├── _posts/          # Blog posts (Markdown)
├── _config.yml      # Jekyll configuration
├── Gemfile          # Ruby dependencies
├── index.markdown   # Home page
├── about.markdown   # About page
└── 404.html         # Custom 404 page
```

---

## Configuration

Key settings in `_config.yml`:

- **title:** This is my first blog
- **email:** 123456789@hotmail.com
- **description:** 上帝不会掷骰子
- **baseurl:** `/Blog`
- **url:** `https://zzj1965186613.github.io`

---

## License

MIT
