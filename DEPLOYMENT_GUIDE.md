# HealUWellness - Xneelo Deployment Guide

## Pre-Deployment Checklist

### 1. Set Up Contact Form
The contact form needs a backend to work. **You must do this BEFORE uploading:**

#### Using Formspree (Recommended - Free & Easy)
1. Go to https://formspree.io
2. Sign up with Debbie@healuwellness.co.za
3. Create a new form
4. Copy your Form ID (looks like: `xpznkqyz`)
5. In `index.html`, find this line (around line 644):
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
6. Replace `YOUR_FORM_ID` with your actual form ID

#### Alternative: Xneelo Form Handler
- Contact Xneelo support to ask if they provide a form-to-email script
- Some Xneelo plans include PHP form handlers

---

## Uploading to Xneelo

### Method 1: File Manager (Easiest)
1. Log into your Xneelo cPanel
2. Open **File Manager**
3. Navigate to `public_html` folder (or `www` - depends on your account)
4. Upload these files/folders:
   - `index.html`
   - `assets/` folder (entire folder with all images)
   - `hero-orchid-banner.png` (if you want to keep it in root)

### Method 2: FTP/SFTP (Faster for multiple files)
1. Get your FTP credentials from Xneelo cPanel
2. Use FileZilla or Cyberduck
3. Connect to your hosting
4. Upload all files to `public_html` or `www`

---

## File Structure on Server
Your server structure should look like this:
```
public_html/
├── index.html
├── assets/
│   ├── heal-u-wellness-logo.png
│   ├── heal-u-wellness-logo_mauve.png
│   ├── hero-orchid-banner.png
│   ├── hero-orchid-banner_photo.png
│   ├── Name.png
│   ├── orchid.png
│   └── container backgrounds/
│       ├── 2.png
│       ├── 3.png
│       ├── 4.png
│       ├── 5.png
│       ├── 6.png
│       ├── 7.png
│       ├── 8.png
│       └── 9.png
└── hero-orchid-banner.png (optional - there's also one in assets/)
```

---

## After Upload: Testing

1. Visit your domain: `http://yourdomainname.co.za`
2. Test all navigation links
3. **Test the contact form** - submit a test message
4. Check all images load properly
5. Test on mobile devices

---

## Common Issues & Solutions

### Images not showing
- Check that `assets` folder uploaded correctly
- Ensure folder names match exactly (case-sensitive)
- Check file permissions (should be 644 for files, 755 for folders)

### Form not working
- Make sure you replaced `YOUR_FORM_ID` with actual Formspree ID
- Check spam folder for form submissions
- Verify email address in Formspree settings

### Site shows "Index of /" instead of website
- Make sure file is named `index.html` (lowercase)
- Upload it directly to `public_html` or `www`

---

## SSL Certificate (HTTPS)
Most Xneelo plans include free SSL. To enable:
1. Go to Xneelo cPanel
2. Find **SSL/TLS** or **Let's Encrypt**
3. Enable SSL for your domain
4. Site will be accessible via `https://`

---

## Performance Optimization (Optional)

### Enable Gzip Compression
Add this to `.htaccess` file in public_html:
```apache
<IfModule mod_deflate.c>
  AddOutputFilterByType DEFLATE text/html text/css text/javascript
</IfModule>
```

### Browser Caching
Add to `.htaccess`:
```apache
<IfModule mod_expires.c>
  ExpiresActive On
  ExpiresByType image/png "access plus 1 year"
  ExpiresByType text/css "access plus 1 month"
</IfModule>
```

---

## Support Contacts
- **Xneelo Support:** https://www.xneelo.co.za/help
- **Formspree Support:** https://help.formspree.io/

---

## Quick Reference: Your Site Details
- **Email:** Debbie@healuwellness.co.za
- **Phone:** 072 482 2593
- **Address:** 2 Morgenster Street, Durbanville Hills, 7550
- **Business:** Heal U Wellness - Red Light Therapy

---

**Need help? Feel free to ask!**
