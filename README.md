# Mark Anthony Morales — Portfolio

Personal portfolio website built with Vue.js 3 + Vite. Bento grid layout with a Warm Navy + Gold color palette, dark/light mode, and responsive design.

**Live site:** `https://<your-username>.github.io/portfolio/`

## Local Development

```bash
npm install
npm run dev
```

Open `http://localhost:5173/portfolio/` in your browser.

## Updating Content

All site content lives in a single file: `src/data/profile.js`. Edit it to update your name, experience, skills, projects, etc. No need to touch component files.

## Deploy to GitHub Pages

### Step 1: Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name the repository **`portfolio`** (must match the base path in `vite.config.js`)
3. Set it to **Public**
4. Do **not** initialize with README, .gitignore, or license (you already have these)
5. Click **Create repository**

### Step 2: Push Your Code

Replace `<your-username>` with your actual GitHub username:

```bash
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/<your-username>/portfolio.git
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/<your-username>/portfolio`
2. Click **Settings** (tab at the top)
3. In the left sidebar, click **Pages**
4. Under **Build and deployment > Source**, select **GitHub Actions**
5. That's it — the workflow at `.github/workflows/deploy.yml` handles the rest

### Step 4: Wait for Deployment

1. Go to the **Actions** tab in your repository
2. You should see a workflow run called "Deploy to GitHub Pages" in progress
3. Wait for it to finish (usually 1-2 minutes)
4. Once complete, your site is live at: `https://<your-username>.github.io/portfolio/`

### Updating the Site

After the initial setup, any push to `main` will automatically rebuild and redeploy:

```bash
git add .
git commit -m "Update portfolio content"
git push
```

## Build for Production

```bash
npm run build     # outputs to dist/
npm run preview   # preview the production build locally
```

## Tech Stack

- **Vue.js 3** (Composition API)
- **Vite** (build tool)
- **Custom CSS** (no frameworks)
- **GitHub Actions** (CI/CD)
- **GitHub Pages** (hosting)
