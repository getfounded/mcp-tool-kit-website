# GitHub Pages Deployment Guide

This repository is configured to deploy automatically to GitHub Pages.

## Setup Instructions

1. **Enable GitHub Pages in your repository:**
   - Go to Settings → Pages
   - Under "Build and deployment", select "GitHub Actions" as the source

2. **The site will automatically deploy when you:**
   - Push changes to the `main` branch
   - Manually trigger the workflow from the Actions tab

## Deployment URL

Once deployed, your site will be available at:
```
https://[your-username].github.io/[repository-name]/
```

For example, if your GitHub username is `johndoe` and your repository is named `mcp-tool-kit-website`, the URL would be:
```
https://johndoe.github.io/mcp-tool-kit-website/
```

## Manual Deployment

To manually trigger a deployment:
1. Go to the Actions tab in your repository
2. Select "Deploy to GitHub Pages" workflow
3. Click "Run workflow"
4. Select the branch and click "Run workflow"

## Troubleshooting

If the deployment fails:
1. Check the Actions tab for error messages
2. Ensure GitHub Pages is enabled in repository settings
3. Verify that the workflow has the necessary permissions

The deployment workflow uses the latest GitHub Actions for Pages deployment, ensuring compatibility and security.