# 🔧 TROUBLESHOOTING: Images Not Showing

## Quick Fix Checklist

### ✅ Step 1: Check Your File Structure on Xneelo

Your files MUST be arranged like this in `public_html`:

```
public_html/
├── index.html
├── favicon.ico
├── style.css
├── hero-orchid-banner.png
└── assets/
    ├── heal-u-wellness-logo.png
    ├── heal-u-wellness-logo_mauve.png
    ├── hero-orchid-banner.png
    ├── hero-orchid-banner_photo.png
    ├── Name.png
    ├── orchid.png
    └── container backgrounds/
        ├── 2.png
        ├── 3.png
        ├── 4.png
        ├── 5.png
        ├── 6.png
        ├── 7.png
        ├── 8.png
        └── 9.png
```

### ✅ Step 2: Verify Assets Folder Uploaded

**In Xneelo File Manager:**
1. Navigate to `public_html`
2. You should see a folder called `assets`
3. Inside `assets` you should see:
   - heal-u-wellness-logo.png ← **LOGO FILE**
   - hero-orchid-banner.png ← **BANNER FILE**
   - container backgrounds folder with 8 PNG files

**If the assets folder is missing or empty:**
- You need to re-upload the entire `assets` folder
- Make sure to upload the folder, not just the files inside it

---

## Common Problems & Solutions

### Problem 1: "Assets folder didn't upload"

**Solution:**
1. In Xneelo File Manager, go to `public_html`
2. Click **Upload** or **New Folder**
3. Create a folder called `assets` if it doesn't exist
4. Open the `assets` folder
5. Upload ALL the files from your local `assets` folder

### Problem 2: "Files uploaded but images still not showing"

**Check file permissions:**
1. In Xneelo File Manager, right-click on `assets` folder
2. Check permissions - should be `755` for folders
3. Check permissions on image files - should be `644`

**Fix permissions in cPanel:**
- Select `assets` folder → Change Permissions → Set to `755`
- Select all image files → Change Permissions → Set to `644`

### Problem 3: "Logo shows but banner doesn't"

The banner image is large (663KB). It might be:
- Still uploading
- Cached in your browser

**Solution:**
1. Wait 1-2 minutes for upload to complete
2. Hard refresh your browser:
   - **Windows:** Ctrl + Shift + R
   - **Mac:** Cmd + Shift + R
3. Clear browser cache

### Problem 4: "Some background images missing"

Check that the `container backgrounds` folder uploaded:
1. Go to `public_html/assets/`
2. Look for `container backgrounds` folder
3. It should contain 8 PNG files (2.png through 9.png)

**If missing:**
- Create folder: `container backgrounds` (with a space!)
- Upload all 8 PNG files into it

---

## Testing Image Paths

**Test if your images are accessible:**

Open these URLs in your browser (replace `yourdomain.co.za` with your actual domain):

1. Logo: `http://yourdomain.co.za/assets/heal-u-wellness-logo.png`
2. Banner: `http://yourdomain.co.za/assets/hero-orchid-banner.png`
3. Favicon: `http://yourdomain.co.za/favicon.ico`

**What you should see:**
- ✅ Images display = Files uploaded correctly, check HTML paths
- ❌ 404 error = Files not uploaded or in wrong location

---

## Step-by-Step Re-Upload

If nothing works, start fresh:

### Using File Manager:
1. Log into Xneelo cPanel
2. Open **File Manager**
3. Navigate to `public_html`
4. **Delete everything** in public_html (or backup first)
5. Extract your ZIP file on your computer
6. Upload **ALL files and folders** at once:
   - Select all files from extracted folder
   - Drag into File Manager
   - Wait for upload to complete (watch progress bar)

### Using FTP (FileZilla):
1. Connect to your Xneelo server
2. Navigate to `public_html` on right side
3. Navigate to your extracted ZIP folder on left side
4. Select all files and folders on left
5. Drag to right side
6. Wait for all transfers to complete

---

## Still Not Working?

### Check Browser Console for Errors:
1. Right-click on your website → Inspect
2. Go to **Console** tab
3. Look for errors like:
   - `404 Not Found` - File doesn't exist
   - `Failed to load resource` - Path is wrong

### Contact Xneelo Support:
If files are uploaded correctly but still not showing:
- Email: support@xneelo.com
- Ask them to check file permissions and paths
- Provide them with the exact error from browser console

---

## Quick Reference: File Paths Used

The website uses these paths:

```html
<!-- Logo (in header) -->
<img src="assets/heal-u-wellness-logo.png">

<!-- Hero Banner (in CSS) -->
background: url("assets/hero-orchid-banner.png")

<!-- Favicon (in head) -->
<link rel="icon" href="favicon.ico">

<!-- Background images (in CSS) -->
url("assets/container%20backgrounds/2.png")
url("assets/container%20backgrounds/3.png")
... etc
```

All paths start from the `public_html` directory.

---

**Need Help?** Share a screenshot of your File Manager showing the public_html folder structure!
