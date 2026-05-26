# 🎂 Sister's Interactive Birthday Website

A beautiful, highly interactive, and personalized birthday website built with **React**, **Vite**, **TypeScript**, and **Tailwind CSS**. It is fully ready to be published on custom platforms or directly uploaded to GitHub!

## ✨ Features
- **🎉 Interactive Hero Section & Birthday Stats**: Real-time counter showing exact stats of how amazing she has been.
- **📜 The Journey So Far**: A beautiful visual, image-free biographical timeline tracking milestones from babyhood to today with elegant icons.
- **🎟️ VIP Birthday Coupons**: Special claims designed by you (e.g. 1 Brother Favor, 1 Day No Annoyance) that can be toggled as used.
- **💬 Random Compliment Generator**: A charming module to generate cute, positive cards and messages with a click.
- **💌 Heartfelt Notes & Surprises**: A beautiful, envelope-style hidden letter signed by **your brother Hitarth Bhatt**.
- **🎈 Aesthetic Effects**: Integrated confetti explosions, floating vector balloons, micro-interaction buttons, and musical controls.

---

## 🛠️ Local Development

### 1. Prerequisites
Ensure you have [Node.js](https://nodejs.org/) installed on your machine.

### 2. Live Setup
Clone or download this repository files into your path:
```bash
# Install dependencies
npm install

# Live preview local dev server
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) (or the port shown in terminal) to see the application.

### 3. Production Build
Generate optimized flat static assets inside the `dist/` directory:
```bash
npm run build
```

---

## 📦 How to Upload to GitHub

1. **Initialize Git** in your project folder:
   ```bash
   git init
   git add .
   git commit -m "feat: initial birthday website ready 🎂"
   ```
2. **Create a new repository** on [github.com](https://github.com) (leave "Add a README" and `.gitignore` unchecked as they are already included inside this project).
3. **Link and push** your local folder:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
   git branch -M main
   git push -u origin main
   ```

---

## 🚀 Easy 1-Click Publishing

Thanks to the relative base configuration (`base: "./"`) pre-configured inside `vite.config.ts`, you can build and publish this website instantly on any cloud platform:

### Choice 1: GitHub Pages (Automatic)
1. Head over to your repository **Settings** on GitHub.
2. Select **Pages** on the left menu.
3. Under **Build and deployment** -> **Source**, choose **GitHub Actions**.
4. Choose the default **Vite / Static site** action helper, or create a simple workflow file under `.github/workflows/deploy.yml` with:
   ```yaml
   name: Deploy to GitHub Pages
   on:
     push:
       branches: [main]
   permissions:
     contents: read
     pages: write
     id-token: write
   jobs:
     deploy:
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v4
         - uses: actions/setup-node@v4
           with:
             node-version: 20
             cache: npm
         - run: npm ci
         - run: npm run build
         - uses: actions/configure-pages@v4
         - uses: actions/upload-pages-artifact@v3
           with:
             path: ./dist
         - id: deployment
           uses: actions/deploy-pages@v4
   ```

### Choice 2: Vercel / Netlify (Easiest)
1. Go to [Vercel](https://vercel.com/) or [Netlify](https://www.netlify.com/).
2. Connect your GitHub account and import your repository.
3. Leave all default build settings as is (Vite build settings are detected automatically).
4. Click **Deploy**! It will be live on a custom sub-domain in less than a minute.
