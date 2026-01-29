# AI Morning Brief Website

A minimalist, professional website for publishing daily AI strategic analysis.

## 📁 File Structure

```
website/
├── index.html              # Homepage with latest brief + archive
├── about.html              # About page with methodology
├── briefs/
│   ├── 20260129.html      # Individual brief pages
│   ├── 20260128.html
│   └── ...
├── assets/
│   ├── og-image.jpg       # Social sharing image (1200x630px)
│   └── favicon.ico
└── README.md              # This file
```

## 🚀 Quick Start

### Option 1: GitHub Pages (Free, Easiest)

1. Create a new GitHub repository (e.g., `ai-morning-brief`)
2. Upload all files to the repository
3. Go to Settings → Pages
4. Select "Deploy from main branch"
5. Your site will be live at `https://yourusername.github.io/ai-morning-brief`

### Option 2: Netlify (Free, Custom Domain)

1. Sign up at [netlify.com](https://netlify.com)
2. Drag and drop the entire `website` folder
3. Site goes live instantly with a random URL
4. Add custom domain in Settings (e.g., `aimorningbrief.com`)

### Option 3: Traditional Hosting

Upload files via FTP to any web host (Bluehost, HostGator, etc.)

## 📝 Adding New Briefs

### Daily Workflow:

1. **Generate the brief** using your automation script:
   ```bash
   python morning_brief_agent_enhanced.py --output briefs/20260130.md
   ```

2. **Convert to HTML** using the template:
   - Copy `briefs/20260129.html` to `briefs/20260130.html`
   - Update the date, title, and content
   - Keep the same structure and styling

3. **Update homepage** (`index.html`):
   - Replace the "Featured Brief" section with new brief
   - Move previous featured brief to "Recent Briefs" archive section
   - Update dates and links

4. **Commit and push** (if using GitHub Pages):
   ```bash
   git add .
   git commit -m "Add brief for Jan 30, 2026"
   git push
   ```

## 🎨 Customization

### Colors
Edit the CSS variables in any HTML file's `<style>` section:
```css
:root {
    --primary: #1a1a1a;      /* Main text color */
    --secondary: #4a4a4a;    /* Secondary text */
    --accent: #0066cc;       /* Links and highlights */
    --light-gray: #f8f9fa;   /* Background accents */
}
```

### Logo
Replace "AI Morning Brief" text in the header with an image:
```html
<a href="/" class="logo">
    <img src="./assets/logo.png" alt="AI Morning Brief" height="30">
</a>
```

### Email Integration

Replace the newsletter form action with your email service:

**Mailchimp:**
```html
<form action="https://yourdomain.us1.list-manage.com/subscribe/post?u=xxx&id=xxx" method="post">
    <input type="email" name="EMAIL" placeholder="your@email.com" required>
    <button type="submit">Subscribe</button>
</form>
```

**ConvertKit:**
```html
<form action="https://app.convertkit.com/forms/xxx/subscriptions" method="post">
    <input type="email" name="email_address" placeholder="your@email.com" required>
    <button type="submit">Subscribe</button>
</form>
```

**Substack:**
Just link to your Substack subscribe page:
```html
<a href="https://yourusername.substack.com/subscribe" class="cta-button">Subscribe</a>
```

## 📱 Social Sharing

### Open Graph Images
Create a 1200x630px image for social sharing and save as `assets/og-image.jpg`. This appears when sharing on LinkedIn/Twitter.

Update the meta tag in each HTML file:
```html
<meta property="og:image" content="https://yourdomain.com/assets/og-image.jpg">
```

### Social Share Buttons
Update the URLs in brief pages:
```html
<!-- LinkedIn -->
<a href="https://www.linkedin.com/sharing/share-offsite/?url=https://yourdomain.com/briefs/20260129.html">

<!-- Twitter -->
<a href="https://twitter.com/intent/tweet?url=https://yourdomain.com/briefs/20260129.html&text=Your headline here">
```

## 🔍 SEO Optimization

### Essential Updates:

1. **Update all meta descriptions** with unique text for each page
2. **Add Google Analytics** (optional):
```html
<!-- Add before </head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

3. **Create sitemap.xml**:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://yourdomain.com/</loc>
    <lastmod>2026-01-29</lastmod>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://yourdomain.com/briefs/20260129.html</loc>
    <lastmod>2026-01-29</lastmod>
    <priority>0.8</priority>
  </url>
</urlset>
```

4. **Create robots.txt**:
```
User-agent: *
Allow: /
Sitemap: https://yourdomain.com/sitemap.xml
```

## 💰 Monetization Options

### 1. Sponsor Slots
Add a sponsor section to briefs:
```html
<div class="sponsor">
    <p class="sponsor-label">Brought to you by</p>
    <a href="https://sponsor.com"><img src="sponsor-logo.png"></a>
</div>
```

### 2. Premium Content
Gate full analysis behind email signup or payment.

### 3. Affiliate Links
Add affiliate disclosures and links to relevant products/services.

## 🛠️ Advanced Features

### Search Functionality
Add a simple search with JavaScript:
```html
<input type="text" id="search" placeholder="Search briefs...">
<script>
  document.getElementById('search').addEventListener('input', function(e) {
    const term = e.target.value.toLowerCase();
    document.querySelectorAll('.archive-item').forEach(item => {
      const text = item.textContent.toLowerCase();
      item.style.display = text.includes(term) ? 'block' : 'none';
    });
  });
</script>
```

### RSS Feed
Create `rss.xml` for feed readers:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0">
  <channel>
    <title>AI Morning Brief</title>
    <link>https://yourdomain.com</link>
    <description>Strategic AI analysis delivered daily</description>
    <item>
      <title>2026's "Show Me the Money" Mandate</title>
      <link>https://yourdomain.com/briefs/20260129.html</link>
      <pubDate>Wed, 29 Jan 2026 06:00:00 GMT</pubDate>
      <description>AI faces ROI reckoning...</description>
    </item>
  </channel>
</rss>
```

## 📊 Performance

This site is optimized for speed:
- No external dependencies
- Minimal CSS/HTML
- Fast loading on all devices
- Perfect Lighthouse scores possible

### Further Optimization:
- Compress images (use [tinypng.com](https://tinypng.com))
- Minify CSS (use [cssminifier.com](https://cssminifier.com))
- Enable CDN (Cloudflare free tier)

## 🐛 Troubleshooting

**Links not working?**
- Check that all `href` paths are correct
- Use relative paths: `./briefs/` not `/briefs/`

**Email signup not working?**
- Verify your email service form action URL
- Check method is `POST`
- Test with a real email address

**Mobile display issues?**
- Clear browser cache
- Test in multiple browsers
- Check viewport meta tag is present

## 📞 Support

Questions? Contact the creator or check:
- GitHub Pages docs: https://pages.github.com
- Netlify docs: https://docs.netlify.com
- HTML/CSS reference: https://developer.mozilla.org

## 📄 License

This template is provided as-is for your use. Customize freely!