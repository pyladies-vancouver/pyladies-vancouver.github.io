# Vancouver PyLadies Static Site

Welcome to the Vancouver PyLadies static site! This project is built with [Hugo](https://gohugo.io/) and uses [Hinode](https://gethinode.com/) as a theme. The site is deployed via [Netlify](https://www.netlify.com/).  


## 🚀 Getting Started  

### **Prerequisites**  
Ensure you have the following installed on your system:  

- [Go](https://go.dev/doc/install)  
- [Hugo](https://gohugo.io/getting-started/installing/) 
- [Node.js](https://nodejs.org/) & [npm](https://www.npmjs.com/)  

### **Installation**  

1. **Clone the repository**  
```sh
git clone https://github.com/yourusername/vancouver-pyladies-site.git
cd vancouver-pyladies-site
```

2.  **Install Hugo Modules**
```sh
hugo mod get -u
```
3. **Install Node.js dependencies for PostCSS processing**
```sh
npm install
```

## 📁 Project Structure

```
├── archetypes/      # Template files for new content
├── assets/          # Uncompiled CSS, JS, images
├── config/          # Settings and options
├── content/         # Site content (Markdown files)
├── layouts/         # HTML templates
├── public/          # Processed static files
├── static/          # Unprocessed static files (copied as-is)
├── go.mod           # Go module definition
├── hinode.work      # Hinode module definition
├── hugo.toml        # Hugo configuration
└── package.json     # Node.js dependencies
```

## ⚒️ Development

**Start Hugo's local development server**
    
```sh
hugo server -D
```

This starts a local server with drafts enabled (-D) and watches for file changes. The site will be available at http://localhost:1313/.

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
This project is licensed under the MIT License.