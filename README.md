# AR Book Scanner Website

Marketing website for the AR Book Scanner iOS app, including Terms of Service and Privacy Policy.

## Files

- `index.html` - Landing page
- `privacy.html` - Privacy Policy
- `terms.html` - Terms of Service
- `support.html` - Support/FAQ page
- `styles.css` - Stylesheet
- `CNAME` - Custom domain configuration (create after setup)

## Deploying to GitHub Pages

### Step 1: Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Create a new repository named `arbookscanner-website` (or any name)
3. Make it **Public** (required for free GitHub Pages)
4. Don't initialize with README (we'll push our files)

### Step 2: Push Website Files

```bash
cd /Users/seanswanick/ARBookScanner/website

# Initialize git repo
git init

# Add all files
git add .

# Commit
git commit -m "Initial website"

# Add your GitHub repo as remote (replace with your username)
git remote add origin https://github.com/YOUR_USERNAME/arbookscanner-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** tab
3. Scroll to **Pages** in the left sidebar
4. Under "Source", select **Deploy from a branch**
5. Select **main** branch and **/ (root)** folder
6. Click **Save**
7. Wait a few minutes - your site will be live at `https://YOUR_USERNAME.github.io/arbookscanner-website/`

## Setting Up Custom Domain

### Step 1: Configure DNS at Your Domain Registrar

Add these DNS records at your domain registrar (e.g., Namecheap, GoDaddy, Google Domains):

**For apex domain (arbookscanner.com):**

| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

**For www subdomain:**

| Type | Name | Value |
|------|------|-------|
| CNAME | www | YOUR_USERNAME.github.io |

### Step 2: Create CNAME File

Create a file named `CNAME` (no extension) in your website folder:

```bash
echo "arbookscanner.com" > CNAME
git add CNAME
git commit -m "Add custom domain"
git push
```

Replace `arbookscanner.com` with your actual domain.

### Step 3: Configure in GitHub

1. Go to repository **Settings** > **Pages**
2. Under "Custom domain", enter your domain (e.g., `arbookscanner.com`)
3. Click **Save**
4. Wait for DNS check (can take up to 24 hours, usually faster)
5. Once verified, check **Enforce HTTPS**

### Step 4: Verify

- Visit `https://arbookscanner.com` (your domain)
- Both `arbookscanner.com` and `www.arbookscanner.com` should work
- HTTPS should be enabled (padlock icon)

## Updating the Website

```bash
cd /Users/seanswanick/ARBookScanner/website

# Make your changes to HTML/CSS files

# Commit and push
git add .
git commit -m "Update website"
git push
```

Changes will be live within a few minutes.

## Important Notes

### Email Addresses

Update these email addresses in the HTML files to your real addresses:
- `privacy@arbookscanner.com` - Privacy inquiries
- `legal@arbookscanner.com` - Legal/Terms inquiries
- `support@arbookscanner.com` - Customer support

You can set these up as email forwards through your domain registrar, or use a service like [ImprovMX](https://improvmx.com/) for free email forwarding.

### App Store Links

Replace the placeholder `href="#"` in the "Download on App Store" buttons with your actual App Store URL once your app is published.

### Legal Disclaimer

While these Terms of Service and Privacy Policy are comprehensive, consider having them reviewed by a legal professional, especially if you plan to operate in multiple jurisdictions or handle significant transaction volumes.

## Customization

### Colors

Edit CSS variables in `styles.css`:

```css
:root {
    --primary: #007AFF;      /* Main brand color */
    --success: #34C759;      /* Hit/success color */
    --text: #1d1d1f;         /* Primary text */
    --text-secondary: #86868b; /* Secondary text */
}
```

### App Icon

Add your app icon as `icon.png` for the Apple touch icon.

### Screenshots

To add app screenshots to the landing page, add images to the repository and update the hero section in `index.html`.
