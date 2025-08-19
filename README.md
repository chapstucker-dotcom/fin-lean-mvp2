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
fin-lean-mvp2/
├─ package.json
├─ vercel.json
└─ pages/
   ├─ index.js
   └─ api/
      └─ chat.js  (optional for AI features)
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
    "react-dom": "18.2.0",
    "openai": "^4.0.0"
  }
}
{
  "version": 2,
  "builds": [
    { "src": "package.json", "use": "@vercel/next" }
  ],
  "routes": [
    { "src": "/(.*)", "dest": "/" }
  ]
}
export default function Home() {
  return (
    <div style={{textAlign: 'center', marginTop: '40px'}}>
      <h1>💸 Findom Lean MVP</h1>
      <p>Welcome to your AI Financial Dominatrix test platform.</p>
    </div>
  );
}
import OpenAI from "openai";

export default async function handler(req, res) {
  if (req.method !== "POST") return res.status(405).end();

  const client = new OpenAI({ apiKey: process.env.OPENAI_API_KEY });
  const { messages } = req.body;

  try {
    const completion = await client.chat.completions.create({
      model: "gpt-4o-mini",
      messages: messages
    });
    res.status(200).json({ reply: completion.choices[0].message.content });
  } catch (e) {
    res.status(500).json({ error: e.message });
  }
}
git add .
git commit -m "Add minimal Next.js MVP structure"
git push origin main
