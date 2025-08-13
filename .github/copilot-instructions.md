# Sol de Acuario - Shamanic Healing Retreats Website

Sol de Acuario is a static HTML website for shamanic healing retreats in Bulgaria's Rose Valley. The site provides information about ceremonies, team members, retreat schedules, and booking.

**ALWAYS reference these instructions first and only fallback to search or bash commands when you encounter unexpected information that does not match what is documented here.**

## Working Effectively

### Bootstrap and Test the Repository
- Clone or ensure you have the repository locally:
  ```bash
  git clone https://github.com/dimitarpeevzautre/soldeacuario.com.git
  cd soldeacuario.com
  ```
- **NO BUILD PROCESS REQUIRED** - This is a static HTML website
- Test the website locally:
  ```bash
  python3 -m http.server 8000 --bind 0.0.0.0
  ```
  - Takes ~1 second to start. NEVER CANCEL.
  - Access at `http://localhost:8000/`
  - Website loads in ~7ms
  - Stop server with `Ctrl+C` or `pkill -f "python3 -m http.server"`

### Validation and Linting
- Install HTML validator:
  ```bash
  pip install html5validator
  ```
  - Installation takes ~30-60 seconds. NEVER CANCEL. Set timeout to 120+ seconds.
- Validate HTML (note: will show false positive for modern CSS):
  ```bash
  html5validator --root . --skip-non-html --format text
  ```
  - Takes ~5-10 seconds. NEVER CANCEL.
  - **EXPECTED**: CSS warning about "scrollbar-width" property - this is a false positive for a valid modern CSS property
  - Exit code 3 is expected due to the CSS warning, but HTML structure is valid

### File Operations and Changes
- All file operations complete in <5ms - extremely fast
- Primary files to modify:
  - `index.html` - Main website content
  - `logo_sol.png` - Website logo (203x214 PNG)
  - `README.md` - Project documentation
- Test changes by refreshing `http://localhost:8000/` in browser

## Validation

### Manual Testing Requirements
- **ALWAYS** serve the website locally after making changes
- **ALWAYS** test these key functionality areas:
  1. **Mobile Menu**: Click hamburger menu button to toggle mobile navigation
  2. **Section Navigation**: Click nav links to verify smooth scrolling to sections
  3. **Form Elements**: Test contact forms and booking form (note: forms do not submit, they are display-only)
  4. **Image Loading**: Verify logo and placeholder images load correctly
  5. **External Resources**: Confirm Tailwind CSS and Google Fonts load from CDN
- **ALWAYS** run html5validator before completing work (accept the CSS warning as expected)
- **NO BUILD VALIDATION NEEDED** - There is no build process to test

### Browser Testing Approach
- Test in multiple browser widths to verify responsive design
- Verify Tailwind CSS classes render correctly
- Check that all sections are accessible via navigation
- Confirm form styling and interactive elements work properly

## Common Tasks

### Repository Structure
```
/home/runner/work/soldeacuario.com/soldeacuario.com/
├── .git/                    # Git repository data
├── .github/                 # GitHub configuration (this file)
├── README.md               # Project documentation (1 line: "# soldeacuario.com")
├── index.html              # Main website file (516 lines)
└── logo_sol.png           # Website logo (33KB PNG)
```

### Key Technologies
- **Framework**: None - Pure HTML/CSS/JavaScript
- **CSS**: Tailwind CSS (loaded via CDN)
- **Fonts**: Google Fonts (Inter and Playfair Display)
- **JavaScript**: Vanilla JS for mobile menu toggle (embedded in HTML)
- **Server**: Any static file server (python3 http.server for development)

### Content Structure (index.html)
- **Header/Navigation** (lines 38-62): Logo, desktop/mobile navigation
- **Hero Section** (lines 66-72): Main landing with call-to-action
- **Team Preview** (lines 78-108): Scrollable team member cards
- **About Section** (lines 111-141): Mission and values
- **Retreats Section** (lines 144-185): Medicine retreat information
- **Medicines Section** (lines 188-227): Detailed plant medicine descriptions
- **Music Section** (lines 230-263): Ceremonial music information
- **Tools Section** (lines 266-296): Shamanic tools showcase
- **Location Section** (lines 299-320): Rose Valley location details
- **Testimonials** (lines 323-353): Customer testimonials
- **Booking Section** (lines 356-402): Retreat booking form
- **FAQ Section** (lines 405-437): Frequently asked questions
- **Contact Section** (lines 440-450): Contact information
- **Footer** (lines 467-496): Links and newsletter signup
- **JavaScript** (lines 498-513): Mobile menu functionality

### Common Modifications
- **Content Updates**: Edit text directly in index.html sections
- **Styling Changes**: Modify Tailwind CSS classes or embedded `<style>` section
- **Images**: Replace logo_sol.png or update placeholder image URLs
- **Navigation**: Update nav links in header section (lines 42-48, 55-60)
- **Forms**: Modify form fields in booking section (lines 382-399)

### Performance Notes
- Website serves in ~7ms locally
- File operations complete in ~2ms
- No build time since it's static HTML
- External CDN resources (Tailwind, fonts) load based on internet connection

### Deployment Considerations
- **Static Hosting**: Can be deployed to any static hosting service (GitHub Pages, Netlify, Vercel, etc.)
- **No Build Step**: Files can be uploaded directly to hosting platform
- **Domain**: Currently configured for soldeacuario.com domain
- **HTTPS**: Recommended for contact forms and user trust

### Troubleshooting
- **Website not loading**: Ensure python server is running on port 8000
- **Styles missing**: Check Tailwind CDN connection (`https://cdn.tailwindcss.com`)
- **Fonts not loading**: Verify Google Fonts CDN access
- **Mobile menu not working**: Check JavaScript in lines 500-512
- **Images not displaying**: Verify file paths and ensure logo_sol.png exists

### Git Workflow
- **Current Branch**: Work on feature branches, merge to main
- **Remote**: https://github.com/dimitarpeevzautre/soldeacuario.com
- **No CI/CD**: No automated build/deploy process configured
- **File Tracking**: Track all files including logo_sol.png and index.html

Remember: This is a simple static website requiring no build process, complex tooling, or lengthy setup procedures. Focus on content accuracy, responsive design, and user experience validation.