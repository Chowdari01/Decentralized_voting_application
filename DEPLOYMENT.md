# Deploying to Vercel

This guide will help you deploy your decentralized voting application to Vercel.

## Prerequisites

1. **Vercel Account**: Sign up at [vercel.com](https://vercel.com)
2. **Git Repository**: Your code should be in a Git repository (GitHub, GitLab, or Bitbucket)
3. **Vercel CLI** (optional): Install with `npm i -g vercel`

## Deployment Steps

### Method 1: Using Vercel Dashboard (Recommended)

1. **Push your code to Git**:
   ```bash
   git add .
   git commit -m "Prepare for Vercel deployment"
   git push origin main
   ```

2. **Connect to Vercel**:
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your Git repository
   - Vercel will automatically detect it's a Python Flask app

3. **Configure Build Settings**:
   - Framework Preset: Other
   - Build Command: Leave empty (Vercel will auto-detect)
   - Output Directory: Leave empty
   - Install Command: `pip install -r requirements.txt`

4. **Environment Variables** (if needed):
   - Add any environment variables in the Vercel dashboard
   - For this app, no additional environment variables are required

5. **Deploy**:
   - Click "Deploy"
   - Vercel will build and deploy your application

### Method 2: Using Vercel CLI

1. **Install Vercel CLI**:
   ```bash
   npm i -g vercel
   ```

2. **Login to Vercel**:
   ```bash
   vercel login
   ```

3. **Deploy**:
   ```bash
   vercel
   ```

4. **Follow the prompts**:
   - Link to existing project or create new
   - Confirm deployment settings
   - Deploy

## Important Notes

### Limitations on Vercel

1. **File Storage**: Vercel uses serverless functions with ephemeral storage. File uploads will be temporary.
2. **DeepFace**: The face verification feature is simulated on Vercel due to computational limitations.
3. **Function Timeout**: Functions have a 30-second timeout limit.

### Production Considerations

For a production deployment, consider:

1. **Cloud Storage**: Use AWS S3, Google Cloud Storage, or similar for file uploads
2. **Database**: Use a cloud database (MongoDB Atlas, PostgreSQL on Railway, etc.)
3. **Face Verification Service**: Use a dedicated service for face verification
4. **Alternative Platforms**: Consider Railway, Heroku, or DigitalOcean for full Flask support

### Environment-Specific Behavior

The app automatically detects if it's running on Vercel and adjusts behavior:
- Uses `/tmp` directory for file uploads
- Simulates face verification instead of using DeepFace
- Optimizes for serverless execution

## Troubleshooting

### Common Issues

1. **Build Failures**:
   - Check that `requirements.txt` is in the root directory
   - Ensure all dependencies are compatible with Python 3.9+

2. **Function Timeouts**:
   - The app is configured for 30-second timeouts
   - For longer operations, consider breaking them into smaller functions

3. **File Upload Issues**:
   - Files are stored temporarily in `/tmp`
   - Implement cloud storage for persistent file storage

### Support

If you encounter issues:
1. Check Vercel deployment logs
2. Review the function logs in Vercel dashboard
3. Test locally first with `python app.py`

## Next Steps

After successful deployment:
1. Test all functionality
2. Set up custom domain (optional)
3. Configure environment variables for production
4. Set up monitoring and logging 