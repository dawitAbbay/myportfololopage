# AWS Cloud Engineering Portfolio Website 🚀

[![AWS](https://img.shields.io/badge/AWS-Amplify-orange)](https://aws.amazon.com/amplify/)
[![HTML5](https://img.shields.io/badge/HTML5-E34C26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 📋 Table of Contents
- [Overview](#overview)
- [Live Demo](#live-demo)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Prerequisites](#prerequisites)
- [Local Development](#local-development)
- [Deployment Methods](#deployment-methods)
- [Project Structure](#project-structure)
- [Customization Guide](#customization-guide)
- [Troubleshooting](#troubleshooting)
- [Resources](#resources)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

A modern, responsive portfolio website designed for AWS Cloud Engineers and developers. This project demonstrates how to deploy a professional portfolio using various AWS services, providing hands-on experience with cloud technologies.

### Learning Objectives
- Deploy a static website using AWS services
- Implement continuous deployment with Git
- Configure custom domains and SSL certificates
- Understand cloud hosting architectures
- Monitor and optimize cloud resources

## 🌐 Live Demo

**Amplify URL:** `https://main.dxxxxxxxxxx.amplifyapp.com` *(Replace with your deployed URL)*

## ✨ Features

### Design Features
- 🎨 **Modern UI/UX** - Clean, professional design with gradient effects
- 📱 **Fully Responsive** - Works seamlessly on all devices
- ⚡ **Performance Optimized** - Fast loading with optimized assets
- 🎭 **Smooth Animations** - Engaging scroll and hover effects
- 🌗 **Professional Color Scheme** - Purple gradient theme

### Technical Features
- 🚀 **AWS Amplify Hosting** - Automatic deployments from Git
- 🔒 **HTTPS Enabled** - Secure by default with SSL
- 🔄 **CI/CD Pipeline** - Automatic updates on git push
- 📊 **CloudWatch Monitoring** - Performance tracking
- 🌍 **Global CDN** - Fast worldwide content delivery

### Portfolio Sections
1. **Hero Section** - Eye-catching introduction with call-to-action
2. **Projects Showcase** - 6 AWS-focused project examples
3. **Skills & Expertise** - Technical skills categorized by domain
4. **Contact Information** - Professional contact details
5. **Social Links** - GitHub, LinkedIn, Twitter integration

## 🛠 Technologies Used

### Frontend
- HTML5 - Semantic markup
- CSS3 - Modern styling with animations
- JavaScript - Interactive features
- Responsive Design - Mobile-first approach

### AWS Services
- **AWS Amplify** - Hosting and CI/CD
- **Route 53** - DNS management (optional)
- **CloudFront** - CDN (included with Amplify)
- **Certificate Manager** - SSL certificates
- **S3** - Static website hosting (alternative method)
- **EC2** - Virtual server hosting (alternative method)

### Development Tools
- Git - Version control
- GitHub - Code repository
- VS Code - Recommended editor
- AWS CLI - Command line tools (optional)

## 📚 Prerequisites

### Required Accounts
- [ ] AWS Account (Free Tier eligible)
- [ ] GitHub Account
- [ ] Git installed locally
- [ ] Text editor (VS Code recommended)

### Recommended Knowledge
- Basic HTML/CSS understanding
- Command line basics
- Git fundamentals
- AWS Console navigation

## 💻 Local Development

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/aws-portfolio-course.git
cd aws-portfolio-course
```

### 2. Open in Browser
```bash
# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

### 3. Make Changes
1. Edit `index.html` in your text editor
2. Refresh browser to see changes
3. Customize content as needed

### 4. Using Live Server (Optional)
```bash
# Install live-server globally
npm install -g live-server

# Run live server
live-server

# Opens at http://localhost:8080
```

## 🚀 Deployment Methods

### Method 1: AWS Amplify (Recommended)

#### Quick Deploy Steps
1. **Fork/Clone this repository**
2. **Push to your GitHub**
3. **Connect to AWS Amplify**
4. **Automatic deployment in 5 minutes!**

#### Detailed Instructions
```bash
# 1. Initialize Git (if not already done)
git init

# 2. Add files
git add .

# 3. Commit
git commit -m "Initial portfolio deployment"

# 4. Add remote origin
git remote add origin https://github.com/YOUR_USERNAME/aws-portfolio-course.git

# 5. Push to GitHub
git push -u origin main

# 6. Go to AWS Amplify Console
# 7. Connect GitHub repository
# 8. Deploy automatically!
```

**Amplify Build Settings:**
```yaml
version: 1
frontend:
  phases:
    build:
      commands: []
  artifacts:
    baseDirectory: /
    files:
      - '**/*'
  cache:
    paths: []
```

### Method 2: S3 Static Hosting with CloudFront

#### S3 Setup
```bash
# Create S3 bucket
aws s3 mb s3://your-portfolio-bucket

# Enable static hosting
aws s3 website s3://your-portfolio-bucket --index-document index.html

# Upload files
aws s3 sync . s3://your-portfolio-bucket --exclude ".git/*"
```

#### CloudFront Distribution
```bash
# Create distribution
aws cloudfront create-distribution \
  --origin-domain-name your-portfolio-bucket.s3-website-region.amazonaws.com \
  --default-root-object index.html
```

**Access via:** `https://dxxxxxxxxxx.cloudfront.net`

### Method 3: EC2 Instance

```bash
# Launch EC2 instance
aws ec2 run-instances --image-id ami-xxxxxxxxx --instance-type t2.micro

# Connect via SSH
ssh -i key.pem ec2-user@instance-ip

# Install web server
sudo yum install httpd -y
sudo systemctl start httpd

# Deploy files
scp -i key.pem index.html ec2-user@instance-ip:/var/www/html/
```

## 📁 Project Structure

```
aws-portfolio-course/
│
├── index.html              # Main portfolio file
├── README.md              # Project documentation
├── LICENSE                # MIT license
│
├── css/                   # Stylesheets (optional)
│   └── styles.css        # External styles
│
├── js/                    # JavaScript (optional)
│   └── script.js         # External scripts
│
├── images/                # Image assets
│   ├── profile.jpg       # Your profile photo
│   ├── project1.png      # Project screenshots
│   └── ...               # Other images
│
└── docs/                  # Documentation
    ├── deployment.md      # Deployment guide
    └── troubleshooting.md # Common issues
```

## 🎨 Customization Guide

### Essential Customizations

1. **Update Personal Information**
```html
<!-- Replace in index.html -->
<div class="logo">[Your Name]</div>
<h1>Your Name - Full Stack Developer</h1>
<p>Your tagline here</p>
```

2. **Update Contact Details**
```html
<a href="mailto:your.email@example.com">your.email@example.com</a>
<a href="tel:+1234567890">+1 (234) 567-890</a>
```

3. **Customize Projects**
```html
<div class="project-card">
    <div class="project-image">Your Project Name</div>
    <div class="project-content">
        <h3>Your Project Title</h3>
        <p>Your project description...</p>
    </div>
</div>
```

4. **Update Skills**
```html
<div class="skill-category">
    <h3>Your Skill Category</h3>
    <div class="skill-list">Your skills here</div>
</div>
```

### Advanced Customizations

#### Change Color Scheme
```css
:root {
    --primary-gradient: linear-gradient(135deg, #YOUR_COLOR_1 0%, #YOUR_COLOR_2 100%);
    --text-dark: #333;
    --text-light: #666;
}
```

#### Add Google Analytics
```html
<!-- Add before </head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

#### Add Custom Sections
```html
<!-- Add new section after skills -->
<section class="section" id="certifications">
    <div class="container">
        <h2>Certifications</h2>
        <div class="cert-grid">
            <!-- Your certifications here -->
        </div>
    </div>
</section>
```

## 🔧 Troubleshooting

### Common Issues & Solutions

#### 1. Amplify Build Fails
```yaml
# Ensure correct build settings in amplify.yml
version: 1
frontend:
  phases:
    build:
      commands: []
  artifacts:
    baseDirectory: /
    files:
      - '**/*'
```

#### 2. GitHub Connection Issues
- Ensure repository is public
- Reconnect GitHub in Amplify Console
- Check GitHub permissions

#### 3. Page Not Loading
- Clear browser cache
- Check DNS propagation (wait 5-10 minutes)
- Verify index.html is in root directory

#### 4. CSS Not Applied
- Check file paths are correct
- Ensure no syntax errors in CSS
- Verify CSS is linked properly in HTML

#### 5. Images Not Showing
- Use relative paths: `./images/photo.jpg`
- Check file extensions (case-sensitive)
- Ensure images are committed to Git

### Debug Commands
```bash
# Check Git status
git status

# View remote origin
git remote -v

# Test HTML locally
python3 -m http.server 8000

# Check AWS CLI configuration
aws configure list

# Verify Amplify app status
aws amplify list-apps
```

## 📚 Resources

### AWS Documentation
- [AWS Amplify Documentation](https://docs.aws.amazon.com/amplify/)
- [AWS Free Tier](https://aws.amazon.com/free/)
- [AWS Training and Certification](https://aws.amazon.com/training/)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)

### Learning Resources
- [HTML/CSS Tutorial - MDN](https://developer.mozilla.org/en-US/docs/Learn)
- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [AWS Skill Builder](https://skillbuilder.aws/)
- [FreeCodeCamp AWS Course](https://www.freecodecamp.org/news/tag/aws/)

### Helpful Tools
- [VS Code](https://code.visualstudio.com/)
- [AWS Toolkit for VS Code](https://aws.amazon.com/visualstudiocode/)
- [Live Server Extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Git Graph Extension](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)

### Video Tutorials
- [AWS Amplify Getting Started](https://www.youtube.com/watch?v=example)
- [S3 Static Hosting Tutorial](https://www.youtube.com/watch?v=example)
- [EC2 Web Server Setup](https://www.youtube.com/watch?v=example)

## 🤝 Contributing

### How to Contribute
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Style Guidelines
- Use semantic HTML5 elements
- Follow CSS BEM naming convention
- Comment complex code sections
- Optimize images before committing
- Test on multiple browsers

### Reporting Issues
- Use GitHub Issues
- Provide detailed description
- Include screenshots if applicable
- Mention browser and OS details

## 📈 Performance Optimization

### Best Practices
1. **Image Optimization**
   - Use WebP format where possible
   - Compress images before upload
   - Use appropriate dimensions

2. **Code Optimization**
   - Minify CSS and JavaScript
   - Remove unused code
   - Use CSS sprites for icons

3. **Caching Strategy**
   - Set appropriate cache headers
   - Use CloudFront caching
   - Implement browser caching

4. **Monitoring**
   - Use AWS CloudWatch
   - Google PageSpeed Insights
   - GTmetrix for performance metrics

## 🔐 Security Considerations

- Always use HTTPS
- Keep dependencies updated
- Use security headers
- Implement CSP (Content Security Policy)
- Regular security audits
- Monitor AWS billing alerts

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 AWS Cloud Engineering Course

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 🎉 Project Completion Checklist

### Core Requirements
- [ ] Portfolio deployed successfully
- [ ] All sections customized with your information
- [ ] Mobile responsive design verified
- [ ] Navigation links working
- [ ] Contact information updated
- [ ] Projects section reflects your work

### Optional Enhancements
- [ ] Custom domain configured
- [ ] SSL certificate active
- [ ] Google Analytics added
- [ ] Performance optimized (90+ PageSpeed)
- [ ] Additional sections added
- [ ] Social media links integrated
- [ ] SEO meta tags added
- [ ] Accessibility features implemented

### Next Steps
1. **Share your portfolio** on LinkedIn and social media
2. **Add new projects** as you complete them
3. **Update skills** as you learn new technologies
4. **Get feedback** from peers and mentors
5. **Consider adding a blog** section
6. **Apply for AWS certifications** to enhance credibility

---

## 💡 Tips for Success

### For Beginners
- Start with Method 1 (AWS Amplify) - it's the simplest
- Don't worry about perfection - iterate and improve
- Ask for help in AWS forums and communities
- Document your learning journey

### For Advanced Users
- Implement Infrastructure as Code (Terraform/CloudFormation)
- Add serverless backend with Lambda
- Integrate with AWS services (DynamoDB, SES)
- Create automated testing pipelines
- Implement A/B testing

---

**Built with ❤️ for AWS Cloud Engineering**

*Last Updated: August 2025*