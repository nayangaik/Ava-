# Phase 2: Deploy to Vercel - Setup Guide

## Prerequisites
- GitHub account (github.com)
- Vercel account (vercel.com)
- Git installed on your system
- Your PINECONE_API_KEY and GROQ_API_KEY ready

---

## Step 1: Initialize & Commit to Local Git

**Check if git is already initialized:**
```bash
cd "C:\Users\NAYAN GAIKWAD\OneDrive\Pictures\Nayanwebdev\Ava-"
git status
```

If you see "fatal: not a git repository", initialize:
```bash
git init
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

**Add files to git:**
```bash
git add .
```

**Commit:**
```bash
git commit -m "Initial commit: Medical chatbot app for Vercel deployment"
```

---

## Step 2: Create GitHub Repository

1. Go to https://github.com/new
2. **Repository name:** `medical-chatbot` (or your preferred name)
3. **Description:** "Medical Chatbot using LangChain, Groq, and Pinecone"
4. **Visibility:** Public (recommended for free Vercel deployment)
5. Click "Create repository"

---

## Step 3: Push Code to GitHub

Copy the commands from GitHub (they will look like this):

```bash
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/medical-chatbot.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

Run these commands in your terminal.

---

## Step 4: Create Vercel Account & Connect GitHub

1. Go to https://vercel.com
2. Click "Sign Up"
3. Choose "Continue with GitHub"
4. Authorize Vercel to access your GitHub account
5. You'll be redirected to Vercel dashboard

---

## Step 5: Import Project to Vercel

1. In Vercel dashboard, click "New Project"
2. Click "Import Git Repository"
3. Search for `medical-chatbot` (or your repo name)
4. Click "Import"

---

## Step 6: Configure Project Settings

1. **Framework Preset:** Select "Other" (since we're using Flask)
2. **Root Directory:** Leave as `.` (root)
3. **Build Command:** Leave empty
4. **Output Directory:** Leave empty
5. **Install Command:** Leave as `pip install -r requirements.txt`
6. Click "Deploy"

---

## Step 7: Set Environment Variables

**IMPORTANT:** Do this BEFORE the first deployment

1. In Vercel dashboard, go to your project
2. Click "Settings" → "Environment Variables"
3. Add these variables:

   **Name:** `PINECONE_API_KEY`
   **Value:** [Your actual Pinecone API key]
   
   **Name:** `GROQ_API_KEY`
   **Value:** [Your actual Groq API key]

4. Click "Save"

---

## Step 8: Redeploy with Environment Variables

1. Go to "Deployments" tab
2. Click the three dots on the latest deployment
3. Select "Redeploy"
4. Wait for deployment to complete

---

## Step 9: Test Your Deployment

1. Once deployment is complete, you'll get a URL (e.g., `https://medical-chatbot.vercel.app`)
2. Click the URL to open your app
3. Try asking the chatbot a question

---

## Troubleshooting

### Deployment Failed?
- Check the logs in Vercel (Deployments → Click deployment → Logs)
- Common issues:
  - Missing environment variables (see Step 7)
  - Timeout (cold start) - normal for first request
  - Module not found - check requirements.txt

### App Loads but No Response?
- Check environment variables are set
- Verify Pinecone index exists and API key is correct
- Verify Groq API key is active

### Performance/Timeout Issues?
- Vercel free tier has 10-second timeout limit
- This might not be enough for LLM calls
- Consider upgrading to Pro plan or optimizing code

---

## What Happens Next?

After successful deployment:
- Every `git push` to main branch will trigger auto-deployment
- You can monitor builds and logs in Vercel dashboard
- Your app is live and accessible worldwide

---

## Summary Checklist

- [ ] Git initialized and code committed
- [ ] GitHub repository created
- [ ] Code pushed to GitHub
- [ ] Vercel account created
- [ ] GitHub connected to Vercel
- [ ] Project imported to Vercel
- [ ] Environment variables set (PINECONE_API_KEY, GROQ_API_KEY)
- [ ] Deployment successful
- [ ] App tested and working

---
