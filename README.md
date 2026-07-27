# 🎬 MR Tube — Hosting & Deployment Guide

## 📁 Files in This Package

| File | URL | Description |
|------|-----|-------------|
| `public/index.html` | `yoursite.com/` | Main website (all pages) |
| `public/admin.html` | `yoursite.com/admin` | Admin portal |
| `vercel.json` | — | Vercel config |
| `netlify.toml` | — | Netlify config |
| `firebase.json` | — | Firebase config |

---

## 🚀 METHOD 1 — Vercel (Recommended · FREE)

### Step 1 — Sign Up
Go to https://vercel.com → Sign up with GitHub or Google

### Step 2 — Deploy (Drag & Drop — No coding!)
1. Go to https://vercel.com/new
2. Click **"Browse"** or drag this entire folder
3. Click **Deploy**
4. ✅ Live in 30 seconds!

### Step 3 — Your URLs
```
Main site:  https://mrtube.vercel.app
Admin:      https://mrtube.vercel.app/admin
```

### Step 4 — Custom Domain (Optional)
1. Vercel Dashboard → Your project → Settings → Domains
2. Add `mrtube.in` or any domain you own
3. Update DNS at your domain registrar

---

## 🌐 METHOD 2 — Netlify (FREE)

### Drag & Drop Deploy
1. Go to https://netlify.com → Sign up
2. Drag the entire `mrtube-deploy` folder onto the deploy area
3. ✅ Done! Gets URL like `mrtube.netlify.app`

---

## 🔥 METHOD 3 — Firebase (Google · FREE tier)

### Install & Deploy
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login to Google
firebase login

# Go to project folder
cd mrtube-deploy

# Initialize (select Hosting only)
firebase init hosting

# Deploy
firebase deploy
```

### Your URLs
```
Main site:  https://mrtube-xyz.web.app
Admin:      https://mrtube-xyz.web.app/admin
```

---

## 🏠 METHOD 4 — Hostinger (₹69–299/month)

1. Buy hosting at https://hostinger.in
2. Login → hPanel → File Manager
3. Go to `public_html` folder
4. Upload `index.html` and `admin.html`
5. ✅ Live immediately!

```
Main site:  https://yourdomain.com
Admin:      https://yourdomain.com/admin.html
```

---

## ☁️ METHOD 5 — AWS S3 + CloudFront (Scalable)

```bash
# Install AWS CLI
pip install awscli

# Configure
aws configure

# Create S3 bucket
aws s3 mb s3://mrtube-hosting

# Enable static hosting
aws s3 website s3://mrtube-hosting --index-document index.html

# Upload files
aws s3 sync public/ s3://mrtube-hosting --acl public-read

# URL:
http://mrtube-hosting.s3-website.ap-south-1.amazonaws.com
```

---

## 🔄 Transfer Between Platforms

### Vercel → Hostinger
1. Download your files
2. Upload to `public_html` in Hostinger File Manager
3. Point domain DNS → Done!

### Vercel → Firebase
1. Copy your files
2. Run `firebase deploy` (see Method 3)
3. Update domain DNS → Done!

### Vercel → AWS
1. Copy files to `public/` folder
2. Run `aws s3 sync` command above
3. Set up CloudFront for CDN → Done!

---

## 🔐 Admin Portal Access

After hosting, go to `/admin` or `/admin.html`

| Role | Email | Password |
|------|-------|----------|
| 👑 CEO | ceo@mrtube.in | CEO@Mrt2025 |
| 🛡️ Super Admin | superadmin@mrtube.in | SAdmin@2025 |
| ⚙️ Admin | admin@mrtube.in | Admin@2025 |
| 📋 Manager | manager@mrtube.in | Mgr@2025 |
| 👩‍💼 HR | hr@mrtube.in | HR@2025 |
| 👮 Moderator | moderator@mrtube.in | Mod@2025 |

---

## 🌍 Custom Domain Setup

### Buy a domain
- **GoDaddy India**: https://godaddy.com/in (₹799/year for .in)
- **Namecheap**: https://namecheap.com (cheaper for .com)
- **Hostinger**: includes free domain with hosting

### Point domain to Vercel
In your domain registrar DNS settings, add:
```
Type: A
Name: @
Value: 76.76.21.21

Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

### Point domain to Firebase
```
Type: A
Name: @
Value: 151.101.1.195

Type: CNAME
Name: www
Value: mrtube-xyz.web.app
```

---

## 📦 Video & Music Storage

Your uploads currently go to **Cloudinary**.
Setup: Go to Admin Portal → Upload tab → Enter your Cloudinary credentials.

**Free Cloudinary**: https://cloudinary.com (25GB free)

For production:
```
Videos → AWS S3 (Mumbai region)
Images → Cloudinary
Database → Firebase Firestore
Auth → Firebase Auth
```

---

## 💰 Cost Summary

| Stage | Platform | Monthly Cost |
|-------|----------|-------------|
| Testing | Vercel + Cloudinary free | ₹0 |
| Launch | Firebase + Cloudinary | ₹0–2,000 |
| Growing | AWS + MongoDB | ₹5,000–15,000 |

---

## 🆘 Need Help?

1. Vercel docs: https://vercel.com/docs
2. Firebase docs: https://firebase.google.com/docs/hosting
3. Netlify docs: https://docs.netlify.com

**Built with ❤️ — MR Tube © 2025**
