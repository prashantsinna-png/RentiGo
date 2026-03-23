# Development Guide 🛠️

Complete guide to developing, extending, and deploying RentiGo.

## Table of Contents

- [Project Architecture](#project-architecture)
- [Local Development Setup](#local-development-setup)
- [File Organization](#file-organization)
- [Code Structure](#code-structure)
- [Adding New Features](#adding-new-features)
- [Debugging](#debugging)
- [Performance Optimization](#performance-optimization)
- [Deployment](#deployment)

---

## Project Architecture

### Frontend Architecture

```
Single HTML File (RentiGo.html)
├── HTML Structure (1000+ lines)
│   ├── Navigation/Header
│   ├── Multiple Pages (divs with class="page")
│   ├── Modals and Overlays
│   └── Toast Notifications
│
├── CSS Styles (1200+ lines)
│   ├── CSS Variables (color, spacing, typography)
│   ├── Reset and Base Styles
│   ├── Component Styles (buttons, cards, forms)
│   ├── Page-specific Styles
│   ├── Responsive Media Queries
│   └── Animations and Transitions
│
└── JavaScript Logic (1300+ lines)
    ├── Utilities (formatting, validation, DOM helpers)
    ├── State Management (localStorage)
    ├── Authentication (login, register, logout)
    ├── Page Rendering Functions
    ├── User Interactions (events, validations)
    └── Dashboard Functions (admin/owner)
```

### Data Flow

```
Browser
  ↓
User Input (Click, Type, Submit)
  ↓
JavaScript Event Handler
  ↓
Validation & Processing
  ↓
Update STATE Object
  ↓
Persist to localStorage
  ↓
Re-render UI (append/update DOM)
  ↓
Display to User
```

### State Structure

```javascript
STATE = {
  users: Array<User>,        // All users
  vehs: Array<Vehicle>,      // All vehicles
  bkgs: Array<Booking>,      // All bookings
  reviews: Array<Review>,    // All reviews
  favs: Array<String>,       // Favorite vehicle IDs
  me: User | null            // Current logged-in user
}
```

---

## Local Development Setup

### Option 1: Quick Start (No Dependencies)

```bash
# 1. Download RentiGo.html
# 2. Open in browser
# That's it! No installation needed.
```

### Option 2: Development Server (Better for testing)

```bash
# Using Python 3
python -m http.server 8000

# Using Python 2
python -m SimpleHTTPServer 8000

# Using Node.js
npm install -g http-server
http-server

# Using PHP
php -S localhost:8000

# Visit: http://localhost:8000/RentiGo.html
```

### Option 3: VS Code Live Server

```bash
# Install extension: "Live Server" by Ritwick Dey
# Right-click RentiGo.html → Open with Live Server
# Or press Alt+L, Alt+O
```

### Browser DevTools

**Accessing Developer Tools:**

Chrome/Edge:
```
F12 or Ctrl+Shift+I (Windows/Linux)
Cmd+Option+I (Mac)
```

Firefox:
```
F12 or Ctrl+Shift+I (Windows/Linux)
Cmd+Option+I (Mac)
```

**Useful DevTools Features:**
- **Console** - See logs, test code
- **Elements** - Inspect DOM
- **Application → Storage → LocalStorage** - View app data
- **Network** - Monitor requests (if backend added)
- **Performance** - Profile speed

---

## File Organization

### Single File Structure

The entire application is in one HTML file for simplicity:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Meta tags, fonts, icons -->
    <!-- ALL CSS IN <style> TAG -->
  </head>
  <body>
    <!-- ALL HTML STRUCTURE -->
    
    <script>
      // ALL JAVASCRIPT LOGIC
    </script>
  </body>
</html>
```

### For Production / Larger Projects

Consider splitting into:

```
/public
  ├── index.html         (minimal structure)
  ├── css/
  │   ├── variables.css
  │   ├── components.css
  │   ├── pages.css
  │   └── responsive.css
  ├── js/
  │   ├── utils.js
  │   ├── state.js
  │   ├── auth.js
  │   ├── pages.js
  │   └── main.js
  └── img/
      └── (images)

/backend
  ├── server.js
  ├── routes/
  ├── models/
  └── middleware/
```

---

## Code Structure

### 1. Utilities & Helpers

```javascript
// DOM selection shorthand
const $ = id => document.getElementById(id);

// Date functions
const today = () => new Date().toISOString().split('T')[0];
const addDays = (d, n) => { /* ... */ };
const diffDays = (a, b) => { /* ... */ };

// Formatting
const fmtMoney = n => '₹' + Number(n).toLocaleString('en-IN');
const fmtDate = d => new Date(d).toLocaleDateString('en-IN', {...});
const initials = name => (name || '?').split(' ').map(...);

// Validation
const validateEmail = e => /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(e.trim());
const validatePhone = p => /^[6-9]\d{9}$/.test(p.trim());

// Security
const escapeHtml = s => String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;');
const mkId = () => '_' + Math.random().toString(36).slice(2, 10);
```

### 2. State Management

```javascript
// Global state
const STATE = {
  users: [...],      // All user objects
  vehs: [...],       // All vehicle objects
  bkgs: [...],       // All booking objects
  reviews: [...],    // All review objects
  favs: [...],       // Array of fav keys
  me: null           // Current user
};

// Persist changes
function persist() {
  localStorage.setItem('rg_users', JSON.stringify(STATE.users));
  localStorage.setItem('rg_vehs', JSON.stringify(STATE.vehs));
  // ... etc
}

// Load on startup
const STATE = {
  users: JSON.parse(localStorage.getItem('rg_users')) || SEED_USERS,
  // ... etc
};
```

### 3. Message Feedback

```javascript
// Toast notifications (temporary messages)
function showToast(msg, type = 'ok') {
  // Types: 'ok', 'err', 'info', 'warn'
}

// Custom confirm dialog
function customConfirm(icon, title, msg, callback, btnLabel, btnClass) {
  // Show modal, execute callback on confirm
}

// Message boxes in forms
function showMsg(elementId, msg, type) {
  // Types: msg-ok, msg-err
}
```

### 4. Page Navigation

```javascript
// Change current page
function showPage(pageName) {
  // Hide all pages, show selected
  // Update navbar highlight
  // Call appropriate render function
  // Scroll to top
}

// Current page tracking
let _currentPage = 'home';

// Page list
const PAGES = ['home', 'auth', 'browse', 'vdetail', 'mybk', 'fleet', 'profile', 'dash'];
```

### 5. Rendering Functions

Each page has a render function:

```javascript
function renderBrowse() {
  // Clear filters
  // Get filtered vehicles from STATE
  // Build HTML strings using buildVCard()
  // Insert into DOM
  // Attach event listeners
}

function renderFleet() {
  // Get current user's vehicles
  // Build HTML for fleet cards
  // Show/hide empty state
  // Attach edit/delete listeners
}

function renderDashboard() {
  // Build sidebar nav
  // Render overview panel with stats
  // Set up panel switching
}
```

### 6. Event Handling

```javascript
// Direct onclick attributes in HTML
<button onclick="submitLogin()">Login</button>

// jQuery-style delegated events in code
document.addEventListener('click', e => {
  if (e.target.matches('.price-chip')) {
    // Handle click
  }
});

// Modal closing with Escape key
document.addEventListener('keydown', e => {
  if (e.key === 'Escape') {
    closeModal();
  }
});
```

### Code Organization Order

The JavaScriptis organized in this order:

1. **Utilities** - Helper functions
2. **Seed Data** - Demo data
3. **State** - Global object
4. **Toast** - Notification system
5. **Auth** - Login/Register
6. **Navbar** - Navigation logic
7. **Pages** - Page render functions
8. **Dashboard** - Admin/Owner views
9. **Modals** - Dialog boxes
10. **Initialization** - DOMContentLoaded

---

## Adding New Features

### Example: Add a Notification System

#### Step 1: Add to HTML

```html
<!-- In modals section -->
<div class="overlay" id="notificationOverlay">
  <div class="modal">
    <div class="modal-hd">
      <span class="modal-title">Notifications</span>
      <button class="modal-x" onclick="closeModal('notificationOverlay')">✕</button>
    </div>
    <div id="notificationList"></div>
  </div>
</div>
```

#### Step 2: Add CSS

```css
/* In <style> block */
.notification-item {
  padding: 12px;
  border-left: 4px solid var(--or);
  background: var(--s);
  margin-bottom: 8px;
  border-radius: 8px;
}
.notification-unread {
  border-left-color: var(--re);
  background: rgba(239, 68, 68, 0.08);
}
```

#### Step 3: Add State

```javascript
// In STATE object
notifications: JSON.parse(localStorage.getItem('rg_notif')) || [],

// Add function to persist
persist();
```

#### Step 4: Add Functions

```javascript
function addNotification(msg, type = 'info') {
  STATE.notifications.push({
    id: mkId(),
    msg,
    type,
    read: false,
    date: today()
  });
  persist();
  showToast(msg, type);
}

function renderNotifications() {
  const list = STATE.notifications.reverse();
  $('notificationList').innerHTML = list.map(n => `
    <div class="notification-item ${!n.read ? 'notification-unread' : ''}">
      <div style="font-size:14px;font-weight:600">${escapeHtml(n.msg)}</div>
      <div style="font-size:12px;color:var(--mu);margin-top:4px">${fmtDate(n.date)}</div>
    </div>
  `).join('');
}

function openNotifications() {
  renderNotifications();
  $('notificationOverlay').classList.add('open');
}
```

#### Step 5: Update Navbar

```html
<!-- Add notification bell button -->
<button class="notif-btn" onclick="openNotifications()">
  <i class="fas fa-bell"></i>
  <span class="notif-dot show" id="notifDot"></span>
</button>
```

#### Step 6: Test

1. Call `addNotification('Test message', 'info')`
2. Click notification bell
3. Verify display
4. Check localStorage persistence

---

## Debugging

### 1. Console Logging

```javascript
// Simple log
console.log('Vehicle count:', STATE.vehs.length);

// Object inspection
console.table(STATE.vehs);

// Timed operations
console.time('search');
// ... code ...
console.timeEnd('search');

// Conditional logging
if (STATE.me?.role === 'admin') {
  console.log('Admin access granted');
}
```

### 2. Breakpoints

In DevTools Console tab:
```javascript
// Set breakpoint in code
debugger;

// Or in code:
if (STATE.me.role === 'admin') debugger;
```

### 3. Data Inspection

```javascript
// Check current user
console.log(STATE.me);

// Check vehicle data
console.log(STATE.vehs.find(v => v.id === 'v1'));

// Check bookings for user
console.log(STATE.bkgs.filter(b => b.cid === STATE.me.id));

// Clear all data (reset to seed)
localStorage.clear();
location.reload();
```

### 4. Common Issues

**Problem:** Page not loading  
**Solution:** Check console for errors, verify `showPage()` is called

**Problem:** Data not persisting  
**Solution:** Ensure `persist()` is called after STATE changes

**Problem:** Buttons not working  
**Solution:** Check function name matches onclick, ensure function is defined

**Problem:** Styling issues  
**Solution:** Check CSS class names, verify selectors in CSS

---

## Performance Optimization

### Current Optimizations

✅ Minimal HTTP requests (everything in one file)  
✅ CSS variables for theme changes  
✅ Event delegation for dynamic content  
✅ Efficient array filtering  
✅ String interpolation with template literals  

### Further Optimizations

```javascript
// ❌ Inefficient
for (let i = 0; i < 1000; i++) {
  $('myElement').innerHTML += '<div>' + i + '</div>';
}

// ✅ Efficient
let html = '';
for (let i = 0; i < 1000; i++) {
  html += '<div>' + i + '</div>';
}
$('myElement').innerHTML = html;
```

```javascript
// ❌ Inefficient
$('vehiclesList').querySelectorAll('.vcard').forEach(card => {
  card.addEventListener('click', openDetail);
});

// ✅ Efficient (delegation)
$('vehiclesList').addEventListener('click', e => {
  const card = e.target.closest('.vcard');
  if (card) openDetail(card.dataset.id);
});
```

---

## Deployment

### Option 1: Static Hosting (Free)

**GitHub Pages:**
```bash
# 1. Push to GitHub
# 2. Settings → Pages → Deploy from main branch
# 3. Access at: https://username.github.io/RentiGo/RentiGo.html
```

**Netlify:**
```bash
# 1. Drag & drop RentiGo.html
# 2. Auto-deployed and live
# 3. Free HTTPS and custom domain support
```

**Vercel:**
```bash
# 1. Visit vercel.com
# 2. Upload RentiGo.html
# 3. Auto-deployed with auto-scaling
```

### Option 2: Server Deployment

**With Node.js + Express:**

```javascript
// server.js
const express = require('express');
const app = express();

app.use(express.static('public'));

app.get('/api/vehicles', (req, res) => {
  // Return vehicle data from database
});

app.post('/api/bookings', (req, res) => {
  // Create booking in database
});

app.listen(5000, () => console.log('Server running'));
```

### Option 3: Docker Container

```dockerfile
FROM node:16-alpine
WORKDIR /app
COPY . .
EXPOSE 5000
CMD ["node", "server.js"]
```

```bash
# Build and run
docker build -t rentigo .
docker run -p 5000:5000 rentigo
```

### Security Checklist

- [ ] Environment variables configured
- [ ] CORS properly set up
- [ ] HTTPS enforced
- [ ] Input validation on backend
- [ ] SQL injection prevention
- [ ] XSS protection
- [ ] Rate limiting enabled
- [ ] Logging configured
- [ ] Error handling complete
- [ ] Testing coverage adequate

---

## Testing

### Manual Testing Checklist

**Authentication:**
- [ ] Login with valid credentials
- [ ] Reject invalid email
- [ ] Reject weak password
- [ ] Logout clears session
- [ ] Can register new user
- [ ] Email uniqueness checked

**Browsing:**
- [ ] Search works
- [ ] Filters work correctly
- [ ] Sort options work
- [ ] Price range filter works
- [ ] Pagination works

**Booking:**
- [ ] Can select dates
- [ ] Price calculates correctly
- [ ] Cannot book past dates
- [ ] Conflict detection works
- [ ] Can cancel bookings

**Admin:**
- [ ] Can approve vehicles
- [ ] Can manage users
- [ ] Can view analytics
- [ ] CSV export works

### Automated Testing (Future)

```javascript
// Example unit test
function testCalculatePrice() {
  const price = calculatePrice(7, 500); // 7 days at ₹500/day
  assert(price === 3500, 'Daily rate calculation failed');
  
  const priceWeekly = calculatePrice(14, 500); // 14 days (1 week)
  assert(priceWeekly < 14 * 500, 'Weekly discount not applied');
  
  console.log('✅ All tests passed');
}
```

---

## Environment Variables (For Production)

Create `.env` file:

```env
# Frontend
VITE_API_URL=https://api.rentigo.com
VITE_APP_NAME=RentiGo

# Backend
PORT=5000
MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/rentigo
JWT_SECRET=your-super-secret-key
JWT_EXPIRY=7d

# Payment
STRIPE_PUBLIC_KEY=pk_live_...
STRIPE_SECRET_KEY=sk_live_...

# Email
SENDGRID_API_KEY=SG.xxx...
SENDGRID_FROM=noreply@rentigo.com

# Third Party
GOOGLE_MAPS_KEY=AIza...
TWILIO_ACCOUNT_SID=AC...
```

---

## Resources & References

- [MDN Web Docs](https://developer.mozilla.org)
- [JavaScript.info](https://javascript.info)
- [CSS-Tricks](https://css-tricks.com)
- [Web Dev Best Practices](https://web.dev/lighthouse-seo)

---

## Support

Need help?
- Check existing issues: GitHub Issues
- Ask questions: GitHub Discussions
- Email: support@rentigo.com

**Happy coding! 🚀**
