# Tydy Legal Documents

This repository contains all legal documents and policies for the Tydy cleaning app, designed for hosting on GitHub Pages.

## 📁 Document Structure

### Core Legal Documents
- **`privacy-policy.md`** - Privacy Policy covering data collection and user rights
- **`terms-of-service.md`** - Terms of Service for app usage and service rules
- **`subscription-terms.md`** - Detailed subscription and billing terms for premium features
- **`eula.md`** - End User License Agreement (references Apple's standard EULA)
- **`copyright-notice.md`** - Copyright and intellectual property information
- **`support-information.md`** - Comprehensive support FAQ and contact information

### Navigation and Presentation
- **`index.html`** - Professional HTML landing page for all legal documents
- **`README.md`** - This file with setup and maintenance instructions

## 🚀 GitHub Pages Setup

### Initial Setup

1. **Create a new repository** for legal documents:
   ```bash
   # Create new repo (do this on GitHub.com)
   # Repository name: tydy-legal-docs
   # Description: Legal documents and policies for Tydy app
   # Public repository (for transparency)
   ```

2. **Upload the documents**:
   ```bash
   git clone https://github.com/[YOUR-USERNAME]/tydy-legal-docs.git
   cd tydy-legal-docs
   
   # Copy all files from legal-docs/ folder to repository root
   cp legal-docs/* .
   
   git add .
   git commit -m "Initial legal documents"
   git push origin main
   ```

3. **Enable GitHub Pages**:
   - Go to repository Settings > Pages
   - Source: Deploy from a branch
   - Branch: main / (root)
   - Save

4. **Your legal documents will be available at**:
   ```
   https://[YOUR-USERNAME].github.io/tydy-legal-docs/
   ```

### Converting Markdown to HTML

GitHub Pages can serve markdown files directly, but for better presentation, convert to HTML:

```bash
# Install pandoc (if not already installed)
brew install pandoc  # macOS
# or
sudo apt-get install pandoc  # Ubuntu

# Convert each markdown file to HTML
pandoc privacy-policy.md -o privacy-policy.html --standalone --css=styles.css
pandoc terms-of-service.md -o terms-of-service.html --standalone --css=styles.css
pandoc subscription-terms.md -o subscription-terms.html --standalone --css=styles.css
pandoc eula.md -o eula.html --standalone --css=styles.css
pandoc copyright-notice.md -o copyright-notice.html --standalone --css=styles.css
pandoc support-information.md -o support-information.html --standalone --css=styles.css
```

## 🎨 Styling and Customization

### Adding CSS Styles

Create a `styles.css` file for consistent document styling:

```css
/* Add to styles.css */
body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    line-height: 1.6;
    max-width: 800px;
    margin: 0 auto;
    padding: 2rem;
    color: #1a2633;
}

h1, h2, h3 { 
    color: #3399ff; 
}

h1 { 
    border-bottom: 2px solid #3399ff; 
    padding-bottom: 0.5rem; 
}

/* Add more styling as needed */
```

### Custom Domain (Optional)

To use a custom domain like `legal.tydy.app`:

1. **Add CNAME file** to repository root:
   ```
   legal.tydy.app
   ```

2. **Configure DNS** with your domain provider:
   - Add CNAME record: `legal` → `[username].github.io`

3. **Update GitHub Pages settings** to use custom domain

## 📱 App Integration

### Update URLs in Tydy App

Once your legal documents are live, update these URLs in your Tydy app:

```swift
// In your app's legal document links
struct LegalURLs {
    static let baseURL = "https://[YOUR-USERNAME].github.io/tydy-legal-docs"
    
    static let privacyPolicy = "\(baseURL)/privacy-policy.html"
    static let termsOfService = "\(baseURL)/terms-of-service.html"
    static let subscriptionTerms = "\(baseURL)/subscription-terms.html"
    static let eula = "\(baseURL)/eula.html"
    static let copyrightNotice = "\(baseURL)/copyright-notice.html"
    static let supportInfo = "\(baseURL)/support-information.html"
    static let legalHub = baseURL // Main navigation page
}
```

### App Store Connect Configuration

Update your App Store Connect listing with the legal document URLs:

1. **App Information > App Review Information**:
   - Privacy Policy URL: `https://[YOUR-URL]/privacy-policy.html`
   - Terms of Use URL: `https://[YOUR-URL]/terms-of-service.html`

2. **App Information > General Information**:
   - Support URL: `https://[YOUR-URL]/support-information.html`

## 🔄 Maintenance and Updates

### Regular Updates

1. **Review documents quarterly** for accuracy and legal compliance
2. **Update dates** in all documents when changes are made
3. **Test all links** to ensure they work correctly
4. **Update app URLs** if document locations change

### Version Control Best Practices

```bash
# When updating documents
git checkout -b update-privacy-policy
# Make your changes
git add privacy-policy.md
git commit -m "Update privacy policy: Add new data collection details"
git push origin update-privacy-policy
# Create pull request and merge
```

### Automated Checks

Consider adding GitHub Actions for automated checks:

```yaml
# .github/workflows/legal-docs-check.yml
name: Legal Documents Check
on: [push, pull_request]
jobs:
  check-links:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Check markdown links
        uses: gaurav-nelson/github-action-markdown-link-check@v1
```

## 📋 Pre-Launch Checklist

Before submitting to App Store:

- [ ] All legal documents are complete and accurate
- [ ] Dates are filled in (replace all `[DATE]` placeholders)
- [ ] Company information is complete (replace `[YOUR ADDRESS]`, etc.)
- [ ] URLs work correctly from the app
- [ ] Documents are mobile-friendly and accessible
- [ ] Email addresses are set up and monitored
- [ ] Privacy policy covers all data collection practices
- [ ] Subscription terms match App Store Connect configuration

## 🔗 Important Links to Update

### Replace These Placeholders

Before going live, replace these placeholders in all documents:

- `[DATE]` - Current date
- `[YEAR]` - Current year
- `[YOUR ADDRESS]` - Your business address
- `[YOUR JURISDICTION]` - Your legal jurisdiction
- `[YOUR TIMEZONE]` - Your support timezone
- `[YOUR WEBSITE]` - Your company website
- `[YOUR SOCIAL HANDLES]` - Social media accounts

### Email Addresses to Set Up

Make sure these email addresses are created and monitored:

- `legal@tydy.app` - Legal and EULA questions
- `privacy@tydy.app` - Privacy policy questions
- `support@tydy.app` - General customer support
- `premium@tydy.app` - Premium subscriber support
- `dmca@tydy.app` - DMCA copyright claims
- `feedback@tydy.app` - Feature requests and feedback
- `bugs@tydy.app` - Bug reports
- `business@tydy.app` - Business partnerships
- `press@tydy.app` - Media inquiries

## 🚨 Legal Disclaimer

These documents are templates and should be reviewed by a qualified attorney before use. Legal requirements vary by jurisdiction and business model. The templates include common provisions but may need customization for your specific situation.

## 📞 Support

For questions about these legal document templates or their implementation:

- **Legal Questions**: Consult with a qualified attorney
- **Technical Setup**: Create an issue in this repository
- **App Integration**: Refer to iOS development documentation

---

**Last Updated**: [DATE]  
**Version**: 1.0  
**Tydy Legal Documents Repository** 