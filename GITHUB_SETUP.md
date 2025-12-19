# GitHub Repository Setup Guide

Your local Git repository is ready! Follow these steps to create and push to GitHub.

## Step 1: Create Repository on GitHub

1. Go to [GitHub.com](https://github.com) and sign in
2. Click the **"+"** icon in the top right → **"New repository"**
3. Fill in the details:
   - **Repository name**: `computational-neuroscience-brain-disorder-prediction` (or your preferred name)
   - **Description**: "Predictive modeling of brain disorders using OASIS-1 MRI data"
   - **Visibility**: Select **"Public"**
   - **DO NOT** initialize with README, .gitignore, or license (we already have these)
4. Click **"Create repository"**

## Step 2: Connect Local Repository to GitHub

After creating the repository, GitHub will show you commands. Use these (replace `YOUR_USERNAME` and `YOUR_REPO_NAME`):

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
```

Or if you prefer SSH:
```bash
git remote add origin git@github.com:YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
```

## Step 3: Verify

Visit your repository on GitHub to confirm all files are uploaded correctly.

## What's Included

✅ All notebook files (step1, step2, step3)  
✅ README.md with project documentation  
✅ Interpretation guides  
✅ Output visualization images  
✅ .gitignore (excludes large data files)

## What's Excluded (via .gitignore)

❌ Data/ folder (too large - users download separately)  
❌ .pkl model files (can be regenerated)  
❌ Large CSV data files (can be regenerated)  
❌ Python cache files

---

**Note**: If you need to update the repository later, use:
```bash
git add .
git commit -m "Your commit message"
git push
```

