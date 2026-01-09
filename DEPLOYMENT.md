# Deployment Guide for TechBee Weekly Status Report Generator

This application is a client-side web application that can be deployed to any static web hosting service.

## Prerequisites

- A web server or static hosting service
- No backend/server-side code required
- All processing happens in the browser

## Deployment Options

### Option 1: GitHub Pages (Free & Easy)

1. **Create a GitHub repository:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/techbee-report-generator.git
   git push -u origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click "Settings" → "Pages"
   - Select "main" branch and "/ (root)" folder
   - Click "Save"
   - Your site will be available at: `https://yourusername.github.io/techbee-report-generator/`

### Option 2: Netlify (Free & Easy)

1. **Sign up at [Netlify](https://www.netlify.com/)**

2. **Deploy:**
   - Drag and drop your project folder to Netlify
   - Or connect your GitHub repository
   - Netlify will automatically deploy your site

3. **Your site will be available at:** `https://your-site-name.netlify.app`

### Option 3: Vercel (Free & Easy)

1. **Install Vercel CLI:**
   ```bash
   npm install -g vercel
   ```

2. **Deploy:**
   ```bash
   vercel
   ```

3. **Follow the prompts to deploy**

### Option 4: Traditional Web Server (Apache/Nginx/IIS)

#### For Apache:
1. Copy all files to your web server directory (e.g., `/var/www/html/` or `C:\xampp\htdocs\`)
2. Ensure `.htaccess` file allows access to all files
3. Access via: `http://your-domain.com/`

#### For Nginx:
1. Copy all files to `/usr/share/nginx/html/` or your configured directory
2. Ensure nginx is running
3. Access via: `http://your-domain.com/`

#### For IIS (Windows Server):
1. Copy all files to `C:\inetpub\wwwroot\` or your website directory
2. Open IIS Manager
3. Add a new website pointing to your directory
4. Access via: `http://your-domain.com/`

### Option 5: Local Network Deployment

1. **Using Python (if installed):**
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   ```
   Access at: `http://localhost:8000`

2. **Using Node.js (if installed):**
   ```bash
   npx http-server -p 8000
   ```
   Access at: `http://localhost:8000`

## File Structure

Your deployment should include these files:
```
techbee-report-generator/
├── index.html          # Landing page
├── admin.html         # Admin panel for file upload
├── dashboard.html     # Dashboard for report display
├── README.md          # Documentation
└── DEPLOYMENT.md      # This file
```

## Important Notes

### CDN Dependencies
The application uses CDN libraries that require internet access:
- **SheetJS (xlsx.js)** - For reading Excel files
- **jsPDF** - For PDF generation
- **html2canvas** - For converting HTML to PDF

If your deployment environment doesn't have internet access, you'll need to:
1. Download the library files
2. Host them locally
3. Update the script tags in HTML files

### Browser Compatibility
- Works best in modern browsers (Chrome, Firefox, Edge, Safari)
- Requires JavaScript enabled
- File upload requires HTML5 support

### Security Considerations
- All processing happens client-side (no data sent to server)
- Excel files are processed in the browser
- No backend security concerns
- Consider HTTPS for production deployment

## Testing After Deployment

1. **Test file upload:**
   - Upload a sample Excel file
   - Verify it processes correctly

2. **Test report generation:**
   - Check that all sheets are displayed
   - Verify summary metrics are extracted

3. **Test PDF download:**
   - Generate a report
   - Download PDF and verify it looks correct

## Troubleshooting

### Issue: Excel files not loading
- **Solution:** Check browser console for errors
- Verify CDN libraries are loading (check Network tab)
- Ensure file format is .xlsx or .xls

### Issue: PDF not generating
- **Solution:** Check browser console for errors
- Verify html2canvas and jsPDF libraries are loaded
- Try a different browser

### Issue: Styles not loading
- **Solution:** Ensure all CSS is in the HTML files (inline styles)
- Check file paths are correct

## Custom Domain Setup

### For GitHub Pages:
1. Add `CNAME` file with your domain name
2. Configure DNS records as per GitHub instructions

### For Netlify/Vercel:
1. Go to domain settings
2. Add your custom domain
3. Follow DNS configuration instructions

## Maintenance

- No server maintenance required
- Update files as needed
- All updates are client-side only

## Support

For issues or questions, check:
- Browser console for errors
- Network tab for failed requests
- Ensure all CDN libraries are accessible

