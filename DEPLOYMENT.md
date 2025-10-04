# Netlify Deployment Setup

This repository is configured for automatic deployment to Netlify. The `netlify.toml` file contains all necessary configuration.

## Quick Setup (5 Minutes)

### Step 1: Connect to Netlify

1. **Log in to Netlify**
   - Go to https://app.netlify.com
   - Sign up or log in with your GitHub account

2. **Import Your Repository**
   - Click "Add new site" → "Import an existing project"
   - Choose "GitHub" as your Git provider
   - Authorize Netlify to access your GitHub account if prompted
   - Select the `djbelieny/djbelieny-site` repository

3. **Configure Build Settings**
   - Netlify will automatically detect the `netlify.toml` configuration
   - Build command: (leave empty)
   - Publish directory: `.`
   - Click "Deploy site"

4. **Done!**
   - Your site will be deployed in 1-2 minutes
   - You'll get a URL like `https://random-name-123.netlify.app`

### Step 2: Customize Your Domain (Optional)

1. In Netlify dashboard, go to **Site settings** → **Domain management**
2. Click **"Add custom domain"** or **"Change site name"**
3. For a custom domain like `djbelieny.com`:
   - Enter your domain name
   - Follow DNS configuration instructions
   - Update your domain registrar's DNS settings

## How Automatic Deployment Works

Once connected to Netlify:

1. **You push code to GitHub** → Netlify detects the change
2. **Netlify automatically builds and deploys** → Takes 1-2 minutes
3. **Your site is live** → Changes appear on your URL

**No additional configuration needed!** Netlify's GitHub integration handles everything automatically.

## What's Included

The repository includes:

- **netlify.toml** - Deployment configuration with:
  - Static file serving setup
  - Security headers
  - Cache optimization for images and assets
  - SPA routing support

## Monitoring Your Deployments

- **Netlify Dashboard**: View all deployments, logs, and site analytics
- **Email Notifications**: Get notified when deployments succeed or fail
- **Deploy Previews**: Each pull request gets its own preview URL

## Custom Domain Setup

To use your own domain (e.g., `djbelieny.com`):

1. In Netlify, go to **Site settings** → **Domain management**
2. Click **"Add custom domain"**
3. Enter `djbelieny.com`
4. Netlify will provide DNS records to add
5. Add these records in your domain registrar (GoDaddy, Namecheap, etc.):
   - **A Record**: Point to Netlify's load balancer IP
   - **CNAME Record**: Point `www` to your Netlify site

Netlify automatically provisions SSL certificates for custom domains.

## Troubleshooting

**Site not updating after push?**
- Check Netlify dashboard for deployment status
- Verify changes were pushed to the `main` branch
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)

**Deployment failed?**
- Check deployment logs in Netlify dashboard
- Verify all files are present in the repository
- Ensure images are in the `images/` directory

**Can't find the site?**
- Look for the site URL in Netlify dashboard under "Site overview"
- Check that you're logged into the correct Netlify account

## Support Resources

- **Netlify Documentation**: https://docs.netlify.com
- **GitHub Repository**: https://github.com/djbelieny/djbelieny-site
- **Netlify Support**: https://www.netlify.com/support/

## Next Steps

After deployment:
1. ✅ Test the site on your Netlify URL
2. ✅ Set up a custom domain (optional)
3. ✅ Configure form submissions if needed
4. ✅ Add analytics (Netlify Analytics available)
5. ✅ Set up branch deploys for staging (optional)
