# Netlify Deployment Setup

This repository is configured for automatic deployment to Netlify via GitHub Actions.

## Initial Setup (One-Time Configuration)

### Option 1: Connect via Netlify Dashboard (Recommended)

1. **Log in to Netlify**
   - Go to https://app.netlify.com
   - Sign up or log in with your GitHub account

2. **Import Your Repository**
   - Click "Add new site" → "Import an existing project"
   - Choose "GitHub" as your Git provider
   - Authorize Netlify to access your GitHub account
   - Select the `djbelieny-site` repository

3. **Configure Build Settings**
   - Build command: Leave empty (static site)
   - Publish directory: `.` (root directory)
   - Click "Deploy site"

4. **Get Your Site Details**
   - After deployment, note your site URL (e.g., `https://your-site-name.netlify.app`)
   - You can customize this URL in Site settings → Domain management

### Option 2: Use GitHub Actions (Advanced)

If you want to use the GitHub Actions workflow included in this repository:

1. **Get Netlify Credentials**
   - Log in to Netlify: https://app.netlify.com
   - Go to User settings → Applications → Personal access tokens
   - Create a new access token and copy it

2. **Create a New Site on Netlify**
   - Click "Add new site" → "Import an existing project"
   - Follow the steps to create the site
   - Copy the Site ID from Site settings → General → Site details

3. **Add GitHub Secrets**
   - Go to your GitHub repository: https://github.com/djbelieny/djbelieny-site
   - Navigate to Settings → Secrets and variables → Actions
   - Click "New repository secret" and add:
     - `NETLIFY_AUTH_TOKEN`: Your Netlify personal access token
     - `NETLIFY_SITE_ID`: Your Netlify site ID

4. **Automatic Deployment**
   - Every push to the `main` branch will trigger automatic deployment
   - Check the "Actions" tab in GitHub to see deployment status

## Continuous Deployment

Once configured, the deployment process is automatic:

- **Push to GitHub** → **Netlify automatically deploys**
- Deployment typically takes 1-2 minutes
- You'll receive deployment notifications in GitHub

## Custom Domain (Optional)

To use your own domain (e.g., djbelieny.com):

1. Go to Netlify Site settings → Domain management
2. Click "Add custom domain"
3. Enter your domain name
4. Follow the DNS configuration instructions
5. Update your domain's DNS records with your domain registrar

## Environment Variables

If you need to add environment variables:

1. Go to Site settings → Environment variables
2. Add your variables
3. Redeploy the site

## Monitoring

- **Netlify Dashboard**: View deployment history, logs, and analytics
- **GitHub Actions**: Check deployment status in the Actions tab
- **Deploy Previews**: Pull requests automatically generate preview deployments

## Troubleshooting

### Deployment Fails
- Check the deployment logs in Netlify dashboard
- Verify all files are committed and pushed to GitHub
- Ensure `netlify.toml` configuration is correct

### GitHub Actions Not Running
- Verify secrets are correctly set in GitHub repository settings
- Check the Actions tab for error messages
- Ensure the workflow file is in `.github/workflows/` directory

### Site Not Updating
- Clear your browser cache
- Check Netlify dashboard to confirm deployment completed
- Verify you pushed changes to the `main` branch

## Support

- Netlify Documentation: https://docs.netlify.com
- GitHub Actions Documentation: https://docs.github.com/en/actions
- Repository: https://github.com/djbelieny/djbelieny-site
