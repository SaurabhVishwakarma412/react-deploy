Part 1: Learning how to deply projects

PART 2: Create React App using Vite
2️⃣ Create Vite + React Project
npm create vite@latest my-react-app

Select options:
✔ Project name: my-react-app
✔ Framework: React
✔ Variant: JavaScript (or TypeScript if you want)

3️⃣ Go to project folder
cd my-react-app

4️⃣ Install dependencies
npm install

5️⃣ Run development server
npm run dev


👉 App runs at: http://localhost:5173

PART 3: Prepare App for GitHub Pages
6️⃣ Install gh-pages
npm install gh-pages --save-dev

7️⃣ Update vite.config.js

Open vite.config.js and add base:

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  base: '/REPOSITORY_NAME/',
})


⚠️ Replace REPOSITORY_NAME with your GitHub repo name
Example:

base: '/react-vite-demo/'

8️⃣ Update package.json

Add homepage and scripts:

{
  "homepage": "https://YOUR_GITHUB_USERNAME.github.io/REPOSITORY_NAME",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  }
}


Example:

"homepage": "https://saurabhvishwakarma412.github.io/react-vite-demo"

PART 4: Push Project to GitHub
9️⃣ Create GitHub Repository

Go to GitHub

Click New Repository

Name: react-vite-demo

Public

❌ Do NOT add README

🔟 Initialize Git & Push Code
git init
git add .
git commit -m "Initial React Vite app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/REPOSITORY_NAME.git
git push -u origin main

PART 5: Deploy to GitHub Pages 🚀
1️⃣1️⃣ Deploy Command
npm run deploy


✔ This creates a gh-pages branch
✔ Uploads production build automatically

PART 6: Enable GitHub Pages
1️⃣2️⃣ Configure GitHub Pages

Go to GitHub Repository → Settings

Click Pages

Under Source:

Branch: gh-pages

Folder: / (root)

Save

PART 7: Access Your Live Website 🌐
🎉 Final URL:
https://YOUR_USERNAME.github.io/REPOSITORY_NAME/
