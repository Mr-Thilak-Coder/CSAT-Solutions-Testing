# GitHub Deployment Guide - CSAT Solutions Website

This guide will help you upload your CSAT Solutions website to GitHub and optionally deploy it using GitHub Pages.

## 📋 Prerequisites

1. **GitHub Account** - Create one at [github.com](https://github.com)
2. **Git Installed** - Download from [git-scm.com](https://git-scm.com/)
3. **All Project Files** - The 10 files from the SEO package

## 🚀 Method 1: Upload via GitHub Web Interface (Easiest)

### Step 1: Create Repository

1. Go to [github.com](https://github.com) and log in
2. Click the **"+"** icon (top right) → **"New repository"**
3. Fill in details:
   - **Repository name:** `csat-solutions-website`
   - **Description:** `Premium branding & marketing agency website - SEO optimized`
   - **Visibility:** Choose **Private** or **Public**
   - ✅ Check **"Add a README file"**
   - **License:** None (or choose one)
4. Click **"Create repository"**

### Step 2: Upload Files via Web

1. In your new repository, click **"Add file"** → **"Upload files"**
2. Drag and drop these files:
   ```
   index.html (rename from index-optimized.html)
   sitemap.xml
   robots.txt
   site.webmanifest
   favicon.ico
   favicon-96x96.png
   favicon.svg
   apple-touch-icon.png
   web-app-manifest-192x192.png
   web-app-manifest-512x512.png
   .gitignore
   ```
3. Add commit message: `Initial commit - SEO optimized website`
4. Click **"Commit changes"**

### Step 3: Upload Documentation (Optional)

1. Click **"Add file"** → **"Create new file"**
2. Name it: `docs/SEO-OPTIMIZATION-REPORT.md`
3. Paste content from SEO-OPTIMIZATION-REPORT.md
4. Commit
5. Repeat for other documentation files

### Step 4: Update README

1. Click on `README.md` in your repository
2. Click the pencil icon (Edit)
3. Replace content with the README.md file provided
4. Commit changes

✅ **Done!** Your website is now on GitHub.

---

## 🖥️ Method 2: Upload via Git Command Line (Recommended)

### Step 1: Install Git

```bash
# Check if Git is installed
git --version

# If not installed, download from: https://git-scm.com/
```

### Step 2: Create GitHub Repository

1. Go to [github.com](https://github.com) and create a new repository (same as Method 1, Step 1)
2. **Don't** initialize with README (we'll add it ourselves)

### Step 3: Prepare Local Files

```bash
# Create a new directory
mkdir csat-solutions-website
cd csat-solutions-website

# Copy all your files here
# Make sure you have:
# - index.html (renamed from index-optimized.html)
# - All favicon files
# - sitemap.xml, robots.txt, site.webmanifest
# - Documentation files
# - README.md
# - .gitignore
```

### Step 4: Initialize Git Repository

```bash
# Initialize Git
git init

# Add all files
git add .

# Create first commit
git commit -m "Initial commit - SEO optimized CSAT Solutions website"
```

### Step 5: Connect to GitHub

```bash
# Add remote repository (replace YOUR-USERNAME)
git remote add origin https://github.com/YOUR-USERNAME/csat-solutions-website.git

# For SSH (if you have SSH keys set up):
# git remote add origin git@github.com:YOUR-USERNAME/csat-solutions-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 6: Verify Upload

1. Go to your GitHub repository URL
2. Verify all files are uploaded
3. Check README displays correctly

✅ **Done!** Your website is now on GitHub.

---

## 🌐 Method 3: Deploy with GitHub Pages (Optional)

GitHub Pages allows you to host your static website for FREE!

### Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **"Settings"** (top menu)
3. Click **"Pages"** (left sidebar)
4. Under **"Source"**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **"Save"**
6. Wait 1-2 minutes for deployment

### Access Your Site

Your site will be available at:
```
https://YOUR-USERNAME.github.io/csat-solutions-website/
```

### Use Custom Domain (Optional)

1. In **Settings → Pages**, add your custom domain: `www.csatsolutions.lk`
2. In your domain registrar (like Namecheap, GoDaddy), add DNS records:
   ```
   Type: CNAME
   Host: www
   Value: YOUR-USERNAME.github.io
   ```
3. Wait for DNS propagation (can take 24-48 hours)

---

## 📁 Recommended Repository Structure

```
csat-solutions-website/
├── .gitignore
├── README.md
├── index.html
├── sitemap.xml
├── robots.txt
├── site.webmanifest
│
├── favicons/
│   ├── favicon.ico
│   ├── favicon-96x96.png
│   ├── favicon.svg
│   ├── apple-touch-icon.png
│   ├── web-app-manifest-192x192.png
│   └── web-app-manifest-512x512.png
│
└── docs/
    ├── SEO-OPTIMIZATION-REPORT.md
    ├── INSTALLATION-GUIDE.md
    └── DEPLOYMENT-GUIDE.md
```

**Note:** If you want this structure, create folders:
```bash
mkdir favicons docs
mv favicon*.* apple-touch-icon.png web-app-manifest*.png favicons/
mv *GUIDE.md *REPORT.md docs/
```

Then update paths in `index.html`:
```html
<!-- Change from: -->
<link rel="icon" href="/favicon.ico">

<!-- To: -->
<link rel="icon" href="/favicons/favicon.ico">
```

---

## 🔄 Updating Your Website

### After Initial Upload

When you make changes to your website:

**Via Web Interface:**
1. Go to the file on GitHub
2. Click pencil icon (Edit)
3. Make changes
4. Commit changes

**Via Git Command Line:**
```bash
# Make your changes locally
# Then:

git add .
git commit -m "Description of changes"
git push origin main
```

### Common Update Commands

```bash
# Check status
git status

# See what changed
git diff

# Pull latest changes from GitHub
git pull origin main

# Push your changes to GitHub
git push origin main

# Create a new branch for testing
git checkout -b feature/new-feature
```

---

## 🔐 Security Best Practices

### 1. Repository Visibility
- Use **Private** repository if contains sensitive info
- Use **Public** repository for open-source projects

### 2. Don't Commit Sensitive Data
Never commit:
- API keys
- Passwords
- Database credentials
- Private configuration files

### 3. Use .gitignore
The provided `.gitignore` file prevents accidentally committing:
- Editor files
- OS files
- Backup files
- Environment variables

### 4. Update Regularly
```bash
# Keep repository updated
git pull origin main  # Before making changes
git push origin main  # After making changes
```

---

## 📊 GitHub Repository Settings

### Recommended Settings

1. **General**
   - ✅ Issues enabled (for bug tracking)
   - ✅ Projects disabled (unless you need it)
   - ✅ Wiki disabled (use docs/ folder instead)

2. **Branches**
   - Protect `main` branch
   - Require pull request reviews (if team)

3. **Actions**
   - Can enable for automated testing/deployment
   - Optional for this project

---

## 🎯 Next Steps After GitHub Upload

1. **Update Repository Description**
   - Add tags: `website`, `seo`, `sri-lanka`, `marketing`, `branding`
   - Add topics for discoverability

2. **Add Repository Badges** (in README)
   ```markdown
   ![Status](https://img.shields.io/badge/Status-Live-success)
   ![SEO](https://img.shields.io/badge/SEO-Optimized-green)
   ```

3. **Set Up GitHub Actions** (Optional)
   - Automated deployment
   - Lighthouse CI for performance testing
   - Broken link checker

4. **Enable Dependabot** (if using npm packages)
   - Automated dependency updates
   - Security vulnerability alerts

5. **Create Project Wiki** (Optional)
   - Detailed documentation
   - Development guidelines
   - API documentation

---

## 🆘 Troubleshooting

### Git not recognized
```bash
# Install Git: https://git-scm.com/downloads
# Or on Mac: brew install git
# Or on Ubuntu: sudo apt install git
```

### Permission denied (GitHub)
```bash
# Use HTTPS with token instead of password
# Or set up SSH keys: https://docs.github.com/en/authentication
```

### Files too large
```bash
# GitHub has 100MB file limit
# Compress large images
# Use Git LFS for large files: https://git-lfs.github.com/
```

### Wrong files committed
```bash
# Remove from Git (keeps local copy)
git rm --cached filename

# Remove from Git and delete
git rm filename

# Commit the removal
git commit -m "Remove filename"
git push origin main
```

### Undo last commit
```bash
# Undo last commit (keeps changes)
git reset --soft HEAD~1

# Undo last commit (discards changes)
git reset --hard HEAD~1
```

---

## 📞 Need Help?

- **Git Documentation:** [git-scm.com/doc](https://git-scm.com/doc)
- **GitHub Docs:** [docs.github.com](https://docs.github.com)
- **GitHub Support:** [support.github.com](https://support.github.com)

---

## ✅ Deployment Checklist

Before deploying to production:

- [ ] All files uploaded to GitHub
- [ ] README.md updated with correct info
- [ ] .gitignore in place
- [ ] GTM ID updated from GTM-XXXXXXX
- [ ] Domain URLs verified
- [ ] Favicon paths correct
- [ ] Documentation included
- [ ] Repository visibility set correctly
- [ ] GitHub Pages configured (if using)
- [ ] Custom domain configured (if applicable)
- [ ] SSL certificate active
- [ ] Analytics tracking verified
- [ ] Contact information updated

---

**Deployment Date:** February 16, 2026  
**Repository:** csat-solutions-website  
**For:** CSAT Solutions  

**Happy deploying!** 🚀
