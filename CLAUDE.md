# CLAUDE.md - Career Site Instructions

## Project Overview
This repository hosts Hidde van Heijst's professional career website, showcasing his expertise as a Cloud Data Architect & Consultant. The site is a static website built with vanilla HTML, CSS, and JavaScript, designed for GitHub Pages hosting.

## Repository Structure
```
/
├── index.html              # Main career website with full professional profile
├── index_modern.html       # Modern version (single line content)
├── resume.html             # Standalone printable resume with PDF generation
├── profielfoto.png        # Profile photo
├── CNAME                  # Custom domain configuration (hiddevanheijst.nl)
├── images/                # Company logos and assets
│   ├── capgemini_logo.png
│   ├── hallmark_logo.jpeg
│   ├── helloprint_logo.png
│   ├── nederlandse_loterij_logo.png
│   ├── stedin_logo.jpg
│   ├── ster.png
│   └── stork_logo.jpg
└── .gitignore            # Git ignore rules
```

## Site Pages

### 1. index.html (Main Career Site)
The primary landing page featuring:
- **Navigation**: Fixed header with smooth scrolling to sections
- **Hero Section**: Professional introduction with data visualization background
- **Services Section**: 6 service cards covering data architecture, engineering, and consulting
- **About Section**: Personal background with profile photo
- **Case Studies**: 4 detailed project showcases with company logos and results
- **Resume Section**: Professional journey, skills, and experience overview
- **Contact Section**: Contact information and call-to-action

**Key Features**:
- Responsive design with CSS Grid and Flexbox
- Professional blue color scheme (#0056b3)
- Smooth scrolling navigation
- Print-optimized styles for resume section
- Interactive elements with hover effects

### 2. resume.html (Standalone Resume)
Dedicated resume page with:
- Clean, professional layout optimized for printing
- PDF generation capability using html2canvas and jsPDF
- Company logos integrated with experience sections
- Print-specific CSS optimization
- Contact information with anti-spam email protection

### 3. index_modern.html
Minimal version (appears to contain only basic HTML structure)

## Technical Implementation

### Styling Architecture
- **No external CSS frameworks** - Custom CSS with modern techniques
- **CSS Grid & Flexbox** for responsive layouts
- **Mobile-first responsive design** with comprehensive breakpoints
- **CSS Variables** for consistent color scheme
- **Media queries** for mobile (≤768px), tablet (769px-1024px), and desktop optimization
- **CSS animations** for interactive elements

### Mobile-First Design Features
- **Hamburger navigation menu** with smooth animations for mobile devices
- **Touch-friendly interface** with proper spacing and button sizes
- **Responsive typography** that scales appropriately across devices
- **Optimized images** that adapt to different screen sizes
- **Mobile-optimized case studies** with stacked layouts for easy reading
- **Collapsible mobile menu** that closes when clicking outside or on links

### JavaScript Features
- Smooth scrolling navigation
- Mobile menu toggle functionality
- Click-outside-to-close mobile menu
- PDF generation (resume.html)
- Anti-spam email obfuscation

### Responsive Breakpoints
- **Mobile**: ≤768px - Single column layouts, hamburger menu, touch-optimized
- **Tablet**: 769px-1024px - Two-column service grids, adjusted typography
- **Desktop**: >1024px - Full multi-column layouts, hover effects

### Performance & SEO
- Optimized images in `/images/` directory
- Semantic HTML structure
- Responsive images with proper alt text
- Fast loading with minimal external dependencies
- Mobile-friendly navigation and touch targets

## Domain & Hosting
- **Custom Domain**: hiddevanheijst.nl (configured via CNAME)
- **Hosting**: GitHub Pages
- **SSL**: Automatic via GitHub Pages

## Content Management

### Professional Information
- **Current Role**: Cloud Data Architect at Nederlandse Loterij
- **Experience**: 7+ years in data engineering and architecture
- **Specialties**: Azure, Python, real-time data processing, compliance systems
- **Industries**: iGaming, retail, e-commerce, fintech, energy

### Case Studies Featured
1. **Nederlandse Loterij**: Real-time gaming compliance platform
2. **Hallmark Benelux**: AI-powered inventory optimization
3. **Capgemini**: Salesforce CDP center of expertise
4. **Stedin**: Smart grid EV charging optimization

### Services Offered
1. Cloud Data Platform Architecture
2. Real-Time Data Engineering
3. Data Strategy & Leadership
4. Data Platform Migration
5. Compliance & Governance
6. Consulting & Training

## Development Guidelines

### Making Updates
1. **Content Changes**: Update HTML files directly for content modifications
2. **Styling Changes**: Modify embedded CSS within each HTML file
3. **New Images**: Add to `/images/` directory and reference appropriately
4. **Testing**: Always test responsive design and print functionality

### Code Style
- **Indentation**: 4 spaces for HTML, CSS
- **CSS Organization**: Group related properties, use consistent formatting
- **Comments**: Add comments for complex CSS sections
- **Naming**: Use descriptive class names and IDs

### Image Optimization
- Company logos should be optimized for web (PNG/JPEG)
- Profile photos should be high quality but web-optimized
- Use appropriate alt text for accessibility

### Print Optimization (resume.html)
- Specific print media queries for optimal PDF output
- Font size adjustments for readability
- Hide unnecessary elements (buttons, decorative elements)
- Ensure proper page breaks

## Deployment
- **Automatic deployment** via GitHub Pages on push to main branch
- **Custom domain** automatically configured via CNAME file
- **HTTPS** enabled by default

## Maintenance Tasks

### Regular Updates
- Keep professional experience current
- Update case studies with new projects
- Refresh testimonials and achievements
- Ensure all links are functional
- Update copyright year in footer

### Performance Monitoring
- Check page load speeds
- Validate HTML/CSS
- Test mobile responsiveness
- Verify print functionality
- Check contact form functionality

### SEO Maintenance
- Update meta descriptions
- Ensure proper heading hierarchy
- Optimize images with descriptive alt text
- Monitor and update structured data

## Contact Information
- **Email**: info@hiddevanheijst.nl
- **LinkedIn**: linkedin.com/in/hiddevanheijst
- **GitHub**: github.com/HiddevH
- **Location**: Hilversum, North Holland, Netherlands

## Business Information
- **KvK**: 97479888 (included in footer)
- **Response Time**: Within 24 hours (as advertised)

---

*This documentation should be updated whenever significant changes are made to the website structure or content.*