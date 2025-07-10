# AWS Static Portfolio Website

A modern, responsive portfolio website built with HTML, CSS, and JavaScript, designed to be hosted on AWS S3 with CloudFront CDN.

## 🚀 Features

- **Responsive Design**: Works perfectly on desktop, tablet, and mobile devices
- **Modern UI**: Clean, professional design with smooth animations
- **Fast Loading**: Optimized for performance and SEO
- **Interactive Elements**: Smooth scrolling, hover effects, and mobile navigation
- **AWS Ready**: Configured for easy deployment to AWS S3 + CloudFront

## 🛠️ Technologies Used

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Icons**: Font Awesome
- **Hosting**: AWS S3 + CloudFront
- **Domain**: AWS Route 53 (optional)

## 📁 Project Structure

```
portfolio/
├── index.html          # Main HTML file
├── styles.css          # CSS styles
├── script.js           # JavaScript functionality
├── deploy.md           # AWS deployment guide
└── README.md           # This file
```

## 🎯 Learning Objectives

This project helps you learn:
- **AWS S3**: Object storage and static website hosting
- **AWS CloudFront**: Content Delivery Network (CDN)
- **AWS Route 53**: Domain management and DNS
- **Web Development**: HTML, CSS, JavaScript
- **Responsive Design**: Mobile-first approach
- **Performance Optimization**: Fast loading websites

## 🏃‍♂️ Quick Start

1. **Clone/Download the project**
2. **Customize the content**:
   - Edit `index.html` to add your information
   - Update contact details and social links
   - Add your projects to the projects section
3. **Test locally**:
   - Open `index.html` in your browser
   - Or use a local server: `python -m http.server 8000`
4. **Deploy to AWS** following the `deploy.md` guide

## ✏️ Customization

### Personal Information
Edit the following in `index.html`:
- Name in the hero section
- About me description
- Skills and technologies
- Contact information
- Social media links

### Styling
Modify `styles.css`:
- Change color scheme (search for hex colors)
- Adjust fonts and sizes
- Modify spacing and layout
- Add new sections

### Functionality
Enhance `script.js`:
- Add new animations
- Implement contact form
- Add more interactive features

## 🌐 Deployment

Follow the detailed deployment guide in `deploy.md` to:
1. Create S3 bucket
2. Configure static website hosting
3. Set up CloudFront distribution
4. Configure custom domain (optional)

## 💰 AWS Costs

**Free Tier Eligible:**
- S3: 5GB storage, 20,000 GET requests/month
- CloudFront: 1TB data transfer, 10,000,000 requests/month
- Route 53: $0.50/month per hosted zone (only if using custom domain)

## 🔧 Local Development

1. **Simple approach**: Open `index.html` in your browser
2. **With local server**:
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Node.js (if you have it)
   npx http-server
   ```
3. **Visit**: `http://localhost:8000`

## 🚀 Next Steps

After mastering this project, try:
1. **Add a contact form** using AWS Lambda and API Gateway
2. **Implement visitor counter** with DynamoDB
3. **Add blog section** with static site generators
4. **Set up CI/CD** with GitHub Actions
5. **Add analytics** with AWS CloudWatch or Google Analytics

## 🤝 Contributing

Feel free to:
- Report issues
- Suggest improvements
- Add new features
- Share your deployed version

## 📚 Resources

- [AWS Free Tier](https://aws.amazon.com/free/)
- [AWS S3 Documentation](https://docs.aws.amazon.com/s3/)
- [CloudFront Documentation](https://docs.aws.amazon.com/cloudfront/)
- [Web Development Resources](https://developer.mozilla.org/en-US/docs/Web)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Happy Learning! 🎉**

Remember: This is your first step into AWS cloud computing. Take your time, experiment, and don't hesitate to explore more AWS services as you grow!