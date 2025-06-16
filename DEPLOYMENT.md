# 🚀 Deployment Guide

This guide covers various deployment options for ReactNeuralEngine, from simple local hosting to production-ready cloud deployments.

## Table of Contents

- [Quick Deployment (XAMPP)](#quick-deployment-xampp)
- [Modern Cloud Platforms](#modern-cloud-platforms)
- [Docker Deployment](#docker-deployment)
- [Traditional Web Hosting](#traditional-web-hosting)
- [Environment Configuration](#environment-configuration)
- [Performance Optimization](#performance-optimization)
- [Troubleshooting](#troubleshooting)

## Quick Deployment (XAMPP)

### Prerequisites
- [XAMPP](https://www.apachefriends.org/) installed
- Downloaded build from [Releases](https://github.com/skynetbee/ReactNeuralEngine/releases)

### Steps
1. Extract the release ZIP file
2. Copy contents to `htdocs/ReactNeuralEngine/`
3. Start Apache in XAMPP Control Panel
4. Visit `http://localhost/ReactNeuralEngine`

## Modern Cloud Platforms

### Vercel (Recommended)

1. **Fork this repository**
2. **Connect to Vercel:**
   - Go to [vercel.com](https://vercel.com)
   - Import your forked repository
   - Deploy automatically

3. **Custom Domain (Optional):**
   ```bash
   vercel --prod
   vercel domains add yourdomain.com
   ```

### Netlify

1. **Fork this repository**
2. **Connect to Netlify:**
   - Go to [netlify.com](https://netlify.com)
   - Connect your GitHub repository
   - Build settings:
     - Build command: `npm run build`
     - Publish directory: `build`

3. **Environment Variables:**
   ```bash
   # In Netlify dashboard > Site settings > Environment variables
   REACT_APP_API_URL=your_api_url
   REACT_APP_ENV=production
   ```

### GitHub Pages

1. **Enable GitHub Pages:**
   - Go to repository Settings > Pages
   - Source: Deploy from a branch
   - Branch: `gh-pages`

2. **Deploy with GitHub Actions:**
   ```bash
   # Workflow automatically deploys on push to main
   git push origin main
   ```

### Firebase Hosting

1. **Install Firebase CLI:**
   ```bash
   npm install -g firebase-tools
   firebase login
   ```

2. **Initialize Firebase:**
   ```bash
   firebase init hosting
   # Choose 'build' as public directory
   # Configure as single-page app: Yes
   ```

3. **Deploy:**
   ```bash
   npm run build
   firebase deploy
   ```

## Docker Deployment

### Production Build

```bash
# Build the image
docker build -t reactneuralengine .

# Run the container
docker run -p 8080:80 reactneuralengine
```

### Development with Docker

```bash
# Using Docker Compose
docker-compose up dev

# Access at http://localhost:3000
```

### Docker Hub Deployment

```bash
# Tag and push to Docker Hub
docker tag reactneuralengine username/reactneuralengine:latest
docker push username/reactneuralengine:latest

# Deploy on any Docker-compatible platform
docker run -p 80:80 username/reactneuralengine:latest
```

## Traditional Web Hosting

### Shared Hosting (cPanel)

1. **Build the project:**
   ```bash
   npm run build
   ```

2. **Upload to server:**
   - Compress the `build` folder
   - Upload via File Manager or FTP
   - Extract in `public_html` or domain folder

3. **Configure .htaccess:**
   ```apache
   Options -MultiViews
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteRule ^ index.html [QSA,L]
   ```

### VPS/Dedicated Server

1. **Install Node.js and Nginx:**
   ```bash
   # Ubuntu/Debian
   curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
   sudo apt-get install -y nodejs nginx
   ```

2. **Clone and build:**
   ```bash
   git clone https://github.com/skynetbee/ReactNeuralEngine.git
   cd ReactNeuralEngine
   npm install
   npm run build
   ```

3. **Configure Nginx:**
   ```nginx
   server {
       listen 80;
       server_name yourdomain.com;
       root /path/to/ReactNeuralEngine/build;
       index index.html;
       
       location / {
           try_files $uri $uri/ /index.html;
       }
   }
   ```

## Environment Configuration

### Environment Variables

Create `.env` files for different environments:

```bash
# .env.local (development)
REACT_APP_API_URL=http://localhost:3001
REACT_APP_ENV=development
REACT_APP_DEBUG=true

# .env.production
REACT_APP_API_URL=https://api.yourdomain.com
REACT_APP_ENV=production
REACT_APP_DEBUG=false
```

### Build-time Configuration

```bash
# Development build
npm start

# Production build
npm run build

# Test build locally
npx serve -s build -l 3000
```

## Performance Optimization

### Build Optimization

1. **Analyze bundle size:**
   ```bash
   npm install -g webpack-bundle-analyzer
   npm run build
   npx webpack-bundle-analyzer build/static/js/*.js
   ```

2. **Enable compression:**
   ```bash
   # Gzip compression in Nginx
   gzip on;
   gzip_types text/css application/javascript application/json;
   ```

### CDN Setup

1. **CloudFlare (Free):**
   - Add your domain to CloudFlare
   - Enable auto-minification
   - Enable Brotli compression

2. **AWS CloudFront:**
   ```bash
   # Use with S3 bucket deployment
   aws s3 sync build/ s3://your-bucket-name --delete
   ```

## Troubleshooting

### Common Issues

**1. Blank Page After Deployment:**
```bash
# Check if homepage is set correctly in package.json
"homepage": "https://yourdomain.com"

# Or use relative paths
"homepage": "./"
```

**2. 404 Errors on Refresh:**
```apache
# Add to .htaccess for Apache
RewriteEngine On
RewriteCond %{DOCUMENT_ROOT}%{REQUEST_URI} -f [OR]
RewriteCond %{DOCUMENT_ROOT}%{REQUEST_URI} -d
RewriteRule ^ - [L]
RewriteRule ^ /index.html [L]
```

**3. Assets Not Loading:**
```bash
# Check build paths in browser developer tools
# Ensure PUBLIC_URL is set correctly
PUBLIC_URL=/subfolder npm run build
```

**4. Environment Variables Not Working:**
```bash
# Must start with REACT_APP_
REACT_APP_API_URL=https://api.example.com

# Restart development server after adding
npm start
```

### Performance Issues

1. **Slow Loading:**
   - Enable gzip compression
   - Use CDN for static assets
   - Optimize images
   - Code splitting

2. **Memory Issues:**
   - Increase Node.js memory limit
   ```bash
   NODE_OPTIONS="--max-old-space-size=4096" npm run build
   ```

### Security Considerations

1. **HTTPS Setup:**
   ```bash
   # Let's Encrypt with Certbot
   sudo certbot --nginx -d yourdomain.com
   ```

2. **Security Headers:**
   ```nginx
   add_header X-Frame-Options "SAMEORIGIN";
   add_header X-XSS-Protection "1; mode=block";
   add_header X-Content-Type-Options "nosniff";
   ```

## Support

If you encounter issues:

- 📖 Check our [Documentation](https://skynetbee.github.io/ReactNeuralEngine/)
- 🐛 Report bugs via [GitHub Issues](https://github.com/skynetbee/ReactNeuralEngine/issues)
- 💬 Ask questions in [Discussions](https://github.com/skynetbee/ReactNeuralEngine/discussions)
- 📧 Contact support: support@reactneuralengine.com

---

<div align="center">
  <p>⭐ Star this repo if this deployment guide helped you!</p>
</div>

