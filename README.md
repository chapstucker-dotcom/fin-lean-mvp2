{
  "version": 2,
  "builds": [
    { "src": "package.json", "use": "@vercel/next" }
  ]
}
# fin-lean-mvp2
lean mvpp
# fin-lean-mvp2

Minimal MVP test project.

## 🚀 Deployment Guide

### 1. Clone or Upload Repo
If not already done, push this repo to GitHub (done ✅).

### 2. Connect to Vercel
1. Go to [Vercel New Project](https://vercel.com/new).
2. Select **chapstucker-dotcom/fin-lean-mvp2** as the repo.
3. Framework: `Other`
4. Root Directory: `/` (root).
5. Build Command: `npm install && npm run build`  
   (or `npm install && npm run dev` if no build step yet).
6. Output Directory: `public`

### 3. Environment Variables (if needed)
Create a `.env` file locally or set them in Vercel:
Add deployment guide to README
{
  "name": "fin-lean-mvp2",
  "version": "1.0.0",
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "14.2.5",
    "react": "18.2.0",
    "react-dom": "18.2.0"
  }
}
