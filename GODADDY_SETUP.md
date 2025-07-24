# GoDaddy Domain Setup for GitHub Pages

This guide will help you connect your GoDaddy domain to your GitHub Pages site.

## Option 1: Using a Subdomain (e.g., www.yourdomain.com)

### Step 1: Add CNAME Record in GoDaddy
1. Log in to your GoDaddy account
2. Go to **My Products** → **Domains**
3. Click **Manage** next to your domain
4. Select **DNS** or **Manage DNS**
5. Add a new record:
   - **Type**: CNAME
   - **Name**: www (or your desired subdomain)
   - **Value**: `[your-username].github.io`
   - **TTL**: 600 seconds (or default)
6. Click **Save**

### Step 2: Configure GitHub Pages
1. In your repository, go to **Settings** → **Pages**
2. Under "Custom domain", enter: `www.yourdomain.com`
3. Click **Save**
4. Check "Enforce HTTPS" (after DNS propagates)

## Option 2: Using Apex Domain (e.g., yourdomain.com)

### Step 1: Add A Records in GoDaddy
1. Log in to your GoDaddy account
2. Go to **My Products** → **Domains**
3. Click **Manage** next to your domain
4. Select **DNS** or **Manage DNS**
5. Add these A records (GitHub's IP addresses):
   - **Type**: A, **Name**: @, **Value**: `185.199.108.153`
   - **Type**: A, **Name**: @, **Value**: `185.199.109.153`
   - **Type**: A, **Name**: @, **Value**: `185.199.110.153`
   - **Type**: A, **Name**: @, **Value**: `185.199.111.153`
6. Add a CNAME record for www:
   - **Type**: CNAME
   - **Name**: www
   - **Value**: `[your-username].github.io`
7. Click **Save**

### Step 2: Configure GitHub Pages
1. In your repository, go to **Settings** → **Pages**
2. Under "Custom domain", enter: `yourdomain.com`
3. Click **Save**
4. Check "Enforce HTTPS" (after DNS propagates)

## Important Notes

- **DNS Propagation**: Changes can take 1-48 hours to take effect
- **HTTPS**: GitHub Pages provides free HTTPS certificates. Enable it after DNS propagates
- **CNAME File**: GitHub will automatically create a CNAME file in your repository

## Verification Steps

1. After DNS propagation, visit your domain
2. Check DNS status: `nslookup yourdomain.com`
3. Verify HTTPS is working properly

## Troubleshooting

### Domain Not Working
- Wait for DNS propagation (up to 48 hours)
- Clear browser cache
- Check DNS records are correct in GoDaddy

### HTTPS Not Working
- Ensure DNS has fully propagated
- Remove and re-add the custom domain in GitHub Pages settings
- Wait 15 minutes and try enabling HTTPS again

### "404 Not Found" Error
- Ensure GitHub Pages is enabled
- Check that deployment workflow has run successfully
- Verify the custom domain is correctly set in GitHub Pages settings