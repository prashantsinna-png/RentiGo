# Contributing to RentiGo 🚗

Thank you for your interest in contributing to RentiGo! This document provides guidelines and instructions for contributing.

## Code of Conduct

Be respectful, inclusive, and constructive in all interactions. We're building something great together!

## How to Contribute

### 1. Reporting Bugs 🐛

**Before submitting a bug report:**
- Check if the issue already exists
- Test with the latest version
- Include browser and OS information
- Provide clear reproduction steps

**Submit bug reports here:**
Create an issue with the label `bug` including:
```
Title: Brief description
Description: 
- Steps to reproduce
- Expected behavior
- Actual behavior
- Browser/OS info
- Screenshots (if applicable)
```

### 2. Suggesting Features 💡

**Feature request process:**
1. Check existing issues/discussions
2. Describe the feature clearly
3. Explain the use case and benefits
4. Provide mockups/examples if possible

**Submit to:** GitHub Discussions with label `enhancement`

### 3. Code Contributions 🔧

#### Getting Started
```bash
# 1. Fork the repository
git clone https://github.com/yourusername/RentiGo.git
cd RentiGo

# 2. Create a feature branch
git checkout -b feature/your-feature-name

# 3. Make your changes
# 4. Test thoroughly
# 5. Commit with clear messages
git commit -m "Add: Brief description of changes"

# 6. Push and create PR
git push origin feature/your-feature-name
```

#### Code Style Guidelines

**JavaScript:**
```javascript
// Use const by default, let when needed
const calculatePrice = (days, dailyRate) => {
  return days * dailyRate;
};

// Use meaningful variable names
const isVehicleAvailable = true;
const userBookingCount = 5;

// Add comments for complex logic
// Calculate best rate based on rental duration
const getOptimalRate = (days, rates) => {
  // ...
};

// Use template literals
const message = `Vehicle ${vehicle.name} booked successfully!`;
```

**CSS:**
```css
/* Use CSS variables for consistency */
:root {
  --primary-color: #f97316;
  --spacing-unit: 8px;
  --border-radius: 10px;
}

/* Organize styles by section */
/* === BUTTONS === */
.btn { /* ... */ }
.btn-primary { /* ... */ }

/* Use meaningful class names */
.vehicle-card-header { /* ... */ }
.booking-card-action { /* ... */ }
```

**HTML:**
```html
<!-- Use semantic HTML -->
<section class="hero">
  <header class="hero-header">
    <h1>Main Title</h1>
  </header>
</section>

<!-- Add data attributes for JS targeting -->
<button data-action="book-vehicle" data-vehicle-id="v1">Book</button>

<!-- Use meaningful IDs and classes -->
<div id="page-browse" class="page"></div>
```

### 4. Pull Request Process

#### Before submitting:
- [ ] Code follows style guidelines
- [ ] No new warnings generated
- [ ] Tested in multiple browsers (Chrome, Firefox, Safari, Edge)
- [ ] Updated documentation if needed
- [ ] Commits are atomic and descriptive

#### PR Template:
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Improvement
- [ ] Documentation update

## Testing
Describe how you tested changes:
- [ ] Tested on Chrome
- [ ] Tested on Firefox
- [ ] Tested on Mobile
- [ ] Tested responsive design

## Screenshots (if applicable)
Include before/after screenshots

## Related Issues
Fixes #123
```

### 5. Documentation Contributions 📚

Help improve our docs:
- Fix typos and clarify explanations
- Add code examples
- Improve API documentation
- Create tutorials or guides

## Development Setup

### Prerequisites
- Modern web browser (latest Chrome, Firefox, Safari, Edge)
- Code editor (VS Code recommended)
- Git for version control
- Optional: Node.js for local testing

### Local Development

```bash
# Clone and navigate
git clone https://github.com/yourusername/RentiGo.git
cd RentiGo

# Start local server (Option 1: Python)
python -m http.server 8000

# Start local server (Option 2: Node.js)
npx http-server

# Visit http://localhost:8000/RentiGo.html
```

### Testing Checklist

Before submitting PR, test:

**Functionality:**
- [ ] Authentication (login/register/logout)
- [ ] Vehicle browsing and search
- [ ] Booking creation and cancellation
- [ ] Profile management
- [ ] Admin functions (if applicable)
- [ ] Data persistence (localStorage)

**Browsers:**
- [ ] Chrome/Chromium
- [ ] Firefox
- [ ] Safari
- [ ] Edge
- [ ] Mobile browsers (iOS Safari, Chrome Mobile)

**Responsive Design:**
- [ ] Desktop (1400px+)
- [ ] Tablet (768px - 1024px)
- [ ] Mobile (< 768px)

**Accessibility:**
- [ ] Keyboard navigation works
- [ ] Tab order is logical
- [ ] Color contrast sufficient
- [ ] Alt text for images

## Branching Strategy

```
main (stable production code)
├── develop (integration branch)
├── feature/user-auth
├── feature/payment-integration
├── bugfix/booking-validation
└── docs/api-documentation
```

**Branch naming:**
- `feature/description` - New features
- `bugfix/description` - Bug fixes
- `improvement/description` - Code improvements
- `docs/description` - Documentation
- `refactor/description` - Code refactoring

## Commit Message Guidelines

```
<type>: <subject>

<body>

<footer>
```

**Types:**
- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation
- `style:` Code style (formatting)
- `refactor:` Code refactoring
- `perf:` Performance improvement
- `test:` Tests
- `chore:` Build, dependencies

**Examples:**
```
feat: Add vehicle image upload functionality
fix: Resolve booking conflict detection bug
docs: Update API documentation
refactor: Optimize vehicle search algorithm
```

## Project File Organization

```
RentiGo.html       # Single app file (organized sections)
├── <head>
│   ├── Meta tags
│   ├── Fonts
│   ├── Icons
│   └── Styles (CSS)
├── <body>
│   ├── Navigation
│   ├── Pages (multiple divs)
│   ├── Modals
│   └── Scripts (JavaScript)
```

### Adding New Pages
1. Create new `<div class="page" id="page-name">`
2. Add navigation link in navbar
3. Add showPage() function call
4. Create render function for content
5. Add styling in the `<style>` block

### Adding New Features
1. **Plan** - Define requirements and flow
2. **Code** - Write HTML/CSS/JS following guidelines
3. **Test** - Test all scenarios and browsers
4. **Document** - Update README if needed
5. **Submit** - Create PR with description

## Performance Guidelines

- Keep functions small and focused
- Use const/let instead of var
- Avoid unnecessary DOM queries
- Cache DOM elements when reused
- Use event delegation for dynamic content
- Optimize asset loading

Example:
```javascript
// ❌ Poor: Query DOM multiple times
function updateUI() {
  $('#vehicle-name').text(name);
  $('#vehicle-name').show();
  $('#vehicle-desc').text(desc);
}

// ✅ Good: Cache references
const nameEl = $('#vehicle-name');
const descEl = $('#vehicle-desc');
nameEl.text(name).show();
descEl.text(desc);
```

## Security Considerations

When contributing code:
- Always validate and sanitize user input
- Use `escapeHtml()` for user-generated content
- Never store sensitive data in localStorage
- Use HTTPS for any external API calls
- Follow OWASP guidelines

## Getting Help

- 💬 **Questions?** Ask in GitHub Discussions
- 🐛 **Found a bug?** Create an Issue
- 📚 **Need docs?** Check README.md
- 💡 **Have an idea?** Start a Discussion

## Recognition

Contributors will be:
- Added to CONTRIBUTORS.md
- Mentioned in release notes
- Credited in the project

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for making RentiGo better! 🎉**

Questions? Open an issue or reach out: support@rentigo.com
