# GitHub Pages Deployment Setup

This project is now configured to be deployed to GitHub Pages automatically.

## Setup Instructions

To complete the deployment setup, follow these steps:

### 1. Enable GitHub Pages

1. Go to your repository on GitHub: https://github.com/kichwee/graplala
2. Click on **Settings** tab
3. In the left sidebar, click on **Pages**
4. Under **Build and deployment**, select:
   - **Source**: GitHub Actions
5. Save the settings

### 2. Trigger the Deployment

The deployment will automatically trigger when you:
- Push to the `main` branch
- Manually trigger the workflow from the Actions tab

To manually trigger:
1. Go to the **Actions** tab in your repository
2. Click on "Deploy to GitHub Pages" workflow
3. Click **Run workflow** button
4. Select the `main` branch and click **Run workflow**

### 3. Access Your Website

Once the deployment is complete, your website will be available at:
```
https://kichwee.github.io/graplala/
```

## What Was Configured

### Next.js Configuration (`next.config.ts`)
- Enabled static export mode (`output: 'export'`)
- Set basePath to `/graplala` for GitHub Pages subdirectory
- Configured unoptimized images for static export compatibility

### GitHub Actions Workflow (`.github/workflows/deploy.yml`)
- Automatically builds the Next.js app on push to main branch
- Generates static files in the `out` directory
- Deploys the static files to GitHub Pages
- Can be manually triggered via workflow_dispatch

## Local Development

To run the project locally:

```bash
npm install
npm run dev
```

To test the production build locally:

```bash
npm run build
```

This will generate the static files in the `out` directory.

## Notes

- The site uses the `/graplala` basePath in production to work correctly on GitHub Pages
- Images are set to `unoptimized: true` because GitHub Pages doesn't support Next.js Image Optimization
- The workflow requires the following permissions: `contents: read`, `pages: write`, `id-token: write`
