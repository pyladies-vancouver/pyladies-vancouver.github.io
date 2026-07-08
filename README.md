# Vancouver PyLadies Static Site

![Logo](https://raw.githubusercontent.com/pyladies-vancouver/pyladies-vancouver.github.io/main/static/img/pyladiesvancouver-square-logo.png)

Welcome to the Vancouver PyLadies static site! This project is built with
[Hugo](https://gohugo.io/) and uses the **Popular** theme (bundled in
`themes/popular`). The site is deployed via [Netlify](https://www.netlify.com/).

## 🚀 Getting Started

### **Prerequisites**

- [Hugo](https://gohugo.io/getting-started/installing/) v0.126.0 or newer.
  The theme uses plain CSS, so the standard (non-extended) Hugo works, and there
  are no Go, Node.js, or Hugo module dependencies.

### **Installation**

**Clone the repository**
```sh
git clone https://github.com/pyladies-vancouver/pyladies-vancouver.github.io.git
cd pyladies-vancouver.github.io
```

That's it — no other install steps.

## 📁 Project Structure

```
├── content/         # Site content (Markdown files)
│   ├── blog/        # Blog posts
│   ├── events/      # Events (upcoming vs past, split by date)
│   ├── organizers/  # Organizer cards
│   ├── handbook.md  # Community handbook (docs page)
│   └── runbooks.md  # Organizer runbooks (docs page)
├── layouts/         # Site-level template overrides
├── static/          # Unprocessed static files (images, PDFs)
├── themes/popular/  # The Popular theme
├── hugo.toml        # Hugo configuration (menu, brand colours, footer)
└── netlify.toml     # Netlify build settings and redirects
```

## ⚒️ Development

**Start Hugo's local development server**

```sh
hugo server
```

The site will be available at http://localhost:1313/.

See the [Meetup Runbooks](https://vancouver.pyladies.com/runbooks/#updating-the-website)
for how the site is edited and deployed.

## 🤝 Contributing

1. Fork the repository
2. Create a new branch:
```bash
git checkout -b your-branch-name
```
3. Make your changes
4. Test your changes locally using `hugo server`
5. Commit your changes:
```bash
git add .
git commit -m "Add your meaningful commit message"
```
6. Push to your fork:
```bash
git push origin your-branch-name
```
7. Create a Pull Request

## 📜 License
This project is licensed under the [MIT license](LICENSE).
