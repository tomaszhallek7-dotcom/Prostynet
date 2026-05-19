# Connect Custom Domain (prostynet.pro) to GitHub Pages

Follow these steps to connect your GoDaddy domain to Prostynet's GitHub Pages.

## 📋 Prerequisites

- ✅ GoDaddy account access
- ✅ Ownership of prostynet.pro domain
- ✅ GitHub account (already have this!)

---

## 🔧 Step 1: Configure GitHub Repository

### 1.1 Add CNAME File to Repository

The CNAME file has been created at the root of your repository with content:
```
prostynet.pro
```

If not present, create it manually:
- File: `CNAME` (no extension)
- Content: `prostynet.pro`

### 1.2 Enable GitHub Pages

1. Go to: https://github.com/tomaszhallek7-dotcom/Prostynet/settings/pages
2. **Source**: Select `main` branch
3. **Custom domain**: Enter `prostynet.pro`
4. Click **Save**
5. ✅ GitHub will automatically create a CNAME file (or use existing one)

---

## 🌐 Step 2: Configure GoDaddy DNS Records

### 2.1 Login to GoDaddy

1. Go to: https://www.godaddy.com
2. Login with your credentials
3. Navigate to **My Domains** → **prostynet.pro**

### 2.2 Access DNS Settings

1. Find **prostynet.pro** in domain list
2. Click the domain name (or **Manage** button)
3. Go to **DNS** tab
4. Click **Manage DNS** (or **Edit DNS Records**)

### 2.3 Add/Update A Records

**Delete existing A records** (if any pointing to wrong IP)

**Add these A records:**

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 1 Hour |
| A | @ | 185.199.109.153 | 1 Hour |
| A | @ | 185.199.110.153 | 1 Hour |
| A | @ | 185.199.111.153 | 1 Hour |

**For www subdomain:**

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | www | tomaszhallek7-dotcom.github.io | 1 Hour |

### 2.4 Update TTL (Optional)

- Change **TTL** to **1 Hour** (600 seconds) for faster propagation
- After propagation complete (24-48h), change back to **1 day** for stability

---

## ✅ Step 3: Verify Configuration

### 3.1 Check DNS Propagation

Use one of these tools to verify:
- https://mxtoolbox.com/
- https://www.nslookup.io/
- `nslookup prostynet.pro` (terminal command)

Expected results:
```
prostynet.pro A 185.199.108.153
prostynet.pro A 185.199.109.153
prostynet.pro A 185.199.110.153
prostynet.pro A 185.199.111.153
www.prostynet.pro CNAME tomaszhallek7-dotcom.github.io
```

### 3.2 Wait for Propagation

- ⏳ Can take 15 minutes to 48 hours
- 🔄 Propagation worldwide varies by region
- 📍 Check status: https://www.whatsmydns.net/

### 3.3 Access Your Site

Once propagated, visit:
- ✅ https://prostynet.pro
- ✅ https://www.prostynet.pro
- ✅ Both should work!

---

## 🔒 Enable HTTPS

GitHub automatically provides FREE SSL certificates!

### 4.1 Enable HTTPS Enforcement

1. Go to: https://github.com/tomaszhallek7-dotcom/Prostynet/settings/pages
2. Check: **✅ Enforce HTTPS**
3. Click **Save**

⚠️ **Wait 5-10 minutes** before enabling - Let GitHub generate certificate first!

---

## 🚀 You're Done!

Your site is now live at:
- 🌐 **https://prostynet.pro**
- 🌐 **https://www.prostynet.pro**

Both URLs redirect to your GitHub Pages site with:
- ✅ Free hosting (GitHub Pages)
- ✅ Free SSL certificate (HTTPS)
- ✅ Auto-deploy from GitHub repo
- ✅ Professional appearance

---

## 🆘 Troubleshooting

### Site not loading after 48 hours?

1. **Check CNAME file exists:**
   ```
   https://github.com/tomaszhallek7-dotcom/Prostynet/blob/main/CNAME
   ```

2. **Verify DNS records in GoDaddy:**
   - All 4 A records added?
   - No typos in values?
   - TTL set correctly?

3. **Clear browser cache:**
   - Ctrl+Shift+Delete (Windows/Linux)
   - Cmd+Shift+Delete (Mac)

4. **Test DNS propagation:**
   - https://www.whatsmydns.net/
   - Search for: prostynet.pro

5. **Contact Support:**
   - 🐛 GitHub Pages Issues: https://github.com/contact
   - 🌐 GoDaddy Support: https://www.godaddy.com/help

---

## 📞 Need Help?

- **GitHub Pages Docs**: https://docs.github.com/en/pages
- **GoDaddy DNS Guide**: https://www.godaddy.com/help/manage-dns-entries-680
- **DNS Propagation Checker**: https://whatsmydns.net/

---

**Created**: 2026-05-19  
**Last Updated**: 2026-05-19  
**Status**: ✅ Ready to Deploy
