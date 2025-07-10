# AWS Static Website Deployment Guide

## Prerequisites
1. AWS Account (Free tier eligible)
2. AWS CLI installed and configured
3. Domain name (optional, for custom domain)

## Step-by-Step Deployment

### Step 1: Create S3 Bucket
1. **Login to AWS Console**
2. **Navigate to S3**
3. **Create Bucket**
   - Bucket name: `your-portfolio-bucket-name` (must be globally unique)
   - Region: Choose closest to your audience
   - **Uncheck "Block all public access"** (We'll configure this properly)
   - Create bucket

### Step 2: Configure Bucket for Static Website Hosting
1. **Select your bucket**
2. **Go to Properties tab**
3. **Scroll down to "Static website hosting"**
4. **Click Edit**
5. **Select "Enable"**
6. **Set Index document**: `index.html`
7. **Set Error document**: `index.html` (for SPA routing)
8. **Save changes**

### Step 3: Set Bucket Policy
1. **Go to Permissions tab**
2. **Scroll to "Bucket policy"**
3. **Click Edit**
4. **Paste this policy** (replace YOUR-BUCKET-NAME):

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
        }
    ]
}
```

### Step 4: Upload Website Files
1. **Go to Objects tab**
2. **Click Upload**
3. **Upload these files**:
   - `index.html`
   - `styles.css`
   - `script.js`
4. **Click Upload**

### Step 5: Test Your Website
1. **Go to Properties tab**
2. **Scroll to "Static website hosting"**
3. **Click the endpoint URL**
4. **Your website should be live!**

## Optional: Add CloudFront CDN

### Step 6: Create CloudFront Distribution
1. **Navigate to CloudFront**
2. **Create Distribution**
3. **Origin Domain**: Select your S3 bucket
4. **Default Root Object**: `index.html`
5. **Create Distribution**
6. **Wait for deployment** (15-20 minutes)

### Benefits of CloudFront:
- Global content delivery
- HTTPS support
- Better performance
- Caching

## Optional: Custom Domain with Route 53

### Step 7: Configure Custom Domain
1. **Purchase domain in Route 53** (or use existing)
2. **Create hosted zone**
3. **Create A record** pointing to CloudFront distribution
4. **Update CloudFront** to use custom domain

## Cost Breakdown (Free Tier)
- **S3**: 5GB storage, 20,000 GET requests/month
- **CloudFront**: 1TB data transfer, 10,000,000 requests/month
- **Route 53**: $0.50/month per hosted zone (if using custom domain)

## Security Best Practices
1. **Use CloudFront** for HTTPS
2. **Enable versioning** on S3 bucket
3. **Set up monitoring** with CloudWatch
4. **Use least privilege** IAM policies

## Troubleshooting
- **403 Forbidden**: Check bucket policy and public access settings
- **404 Not Found**: Verify file names and paths
- **Slow loading**: Consider enabling CloudFront
- **Mixed content**: Ensure all resources use HTTPS

## Next Steps
1. **Add monitoring** with CloudWatch
2. **Set up automated deployment** with GitHub Actions
3. **Add contact form** with Lambda functions
4. **Implement analytics** with Google Analytics or AWS Analytics

## Useful Commands

### AWS CLI Commands (if you have AWS CLI installed):
```bash
# Sync files to S3
aws s3 sync . s3://your-bucket-name --exclude "*.md" --exclude ".git/*"

# Invalidate CloudFront cache
aws cloudfront create-invalidation --distribution-id YOUR-DISTRIBUTION-ID --paths "/*"
```

## Resources
- [AWS S3 Static Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
- [CloudFront Documentation](https://docs.aws.amazon.com/cloudfront/)
- [Route 53 Documentation](https://docs.aws.amazon.com/route53/)