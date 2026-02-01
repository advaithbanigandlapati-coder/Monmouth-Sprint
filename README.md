# Monmouth Sprint Website

A warm-palette, single-page website for volleyball teams featuring news, player rankings, polls, file sharing, and bulletin boards.

![House Icon](house-icon.svg)

## 🌅 Features

- **Home Page** - Hero section with scrollable credits
- **News** - Team announcements and articles
- **Rankings** - V10 player performance metrics with interactive sliders
- **Files** - Password-protected file access (Google Docs integration)
- **Polls** - Team voting system with real-time results
- **Plans Board** - Interactive post-it note bulletin board
- **Contact** - Team contact information and message form

## 🎨 Design

The website features a warm color palette with:
- Sunset Orange (#FF6B35)
- Terracotta (#D65A31)
- Warm Amber (#F7931E)
- Sand (#F4E5D3)
- Cream (#FFF8F0)

Typography: Bebas Neue (headings) + Inter (body)

## 🚀 Quick Start

1. Open `index.html` in any modern web browser
2. Navigate using the top menu
3. Default passwords:
   - Files: `RishuNoTishu`
   - Bulletin Board: `Swaydih`
   - Polls: `Rautmare67`

## 📱 Mobile Support

Fully responsive design optimized for:
- Desktop (1920px+)
- Tablet (768px - 1024px)
- Mobile (320px - 767px)

## 🔧 Customization Guide

### Changing Colors

Find the CSS `:root` variables at the top of the `<style>` section:

```css
:root {
    --sunset-orange: #FF6B35;
    --terracotta: #D65A31;
    --warm-amber: #F7931E;
    /* ...etc */
}
```

Replace hex codes with your preferred colors. Use [Coolors.co](https://coolors.co) for palette generation.

### Adding/Editing Players

Locate the `playersData` array in the JavaScript section:

```javascript
const playersData = [
    {
        name: "Player Name",
        overall: 8.5,  // Out of 10
        description: "Brief player description",
        stats: {
            reflexes: 85,    // 0-100
            spikes: 90,      // 0-100
            sets: 75,        // 0-100
            bumps: 80,       // 0-100
            safety: 95,      // 0-100
            logic: 88,       // 0-100
            teamwork: 92     // 0-100
        }
    }
    // Add more players...
];
```

**Skill Levels:**
- 0-29: Beginner
- 30-59: Intermediate
- 60-84: Advanced
- 85-100: Expert

### Managing News Articles

Add articles in the `#news` page section:

```html
<div class="news-article">
    <h2>Article Title</h2>
    <div class="news-meta">
        <span class="news-date">Month Day, Year</span>
        <span class="news-category">Category</span>
    </div>
    <p>Article content goes here...</p>
</div>
```

**Suggested Categories:** Tournament, Schedule, Player Feature, Facility Update, Community, Achievement, Training

### Updating Passwords

**Files Password (default: RishuNoTishu)**
```javascript
function unlockFiles() {
    if (password === 'RishuNoTishu') {  // ← Change this
        // ...
    }
}
```

**Bulletin Board Password (default: Swaydih)**
```javascript
function unlockBulletin() {
    if (password === 'Swaydih') {  // ← Change this
        // ...
    }
}
```

**Polls Password (default: Rautmare67)**
```javascript
function unlockPolls() {
    if (password === 'Rautmare67') {  // ← Change this
        // ...
    }
}
```

⚠️ **Security Note:** These passwords are visible in the source code. For real security, implement a backend server.

### Changing Fonts

1. Visit [Google Fonts](https://fonts.google.com)
2. Select your fonts
3. Replace the font import in `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=YourFont:wght@400;700&display=swap" rel="stylesheet">
```

4. Update CSS:

```css
/* Headings */
.hero-title, .page-title, .player-name {
    font-family: 'YourDisplayFont', sans-serif;
}

/* Body text */
body, p, input, textarea {
    font-family: 'YourBodyFont', sans-serif;
}
```

**Popular Combinations:**
- Modern: Montserrat + Open Sans
- Bold: Oswald + Roboto
- Classic: Playfair Display + Lato
- Energetic: Fredoka One + Nunito

### Adjusting Animations

Control animation speed by changing duration values:

```css
/* Transitions (hover effects) */
transition: all 0.3s ease;  /* Increase to slow down */

/* Animations (page loads) */
animation: fadeIn 0.6s ease;  /* Increase to slow down */
```

To disable animations, comment them out:
```css
/* animation: fadeIn 0.6s ease; */
```

### Pre-loading Bulletin Board Items

Edit the `bulletinItems` array:

```javascript
const bulletinItems = [
    { date: 'Feb 5, 2026', text: 'Team photos Friday at 3 PM' },
    { date: 'Feb 3, 2026', text: 'Pizza party after Saturday game' }
];
```

### Creating Polls

After unlocking with password, polls can be created with any question. Users can vote by entering their name and selecting Yes/Maybe/No.

### Updating Contact Information

Replace GitHub and email in the contact section:

```html
<a href="https://github.com/yourusername" target="_blank" class="contact-link">
    <div class="contact-icon">📁</div>
    <div class="contact-label">GitHub</div>
    <div class="contact-value">@yourusername</div>
</a>
```

### Updating Credits

Find the credits section in the home page:

```html
<div class="credits-section">
    <h2 class="credits-title">Credits</h2>
    <ul class="credits-list">
        <li class="credits-item">
            <div class="credits-label">Created By</div>
            <div class="credits-value">Your Name</div>
        </li>
        <!-- Add more credits... -->
    </ul>
</div>
```

## 📁 File Structure

```
MonmouthFiles/
├── index.html              # Main website file
├── favicon.ico             # Browser tab icon (32x32)
├── favicon-16x16.png       # Small favicon
├── favicon-32x32.png       # Standard favicon
├── favicon-192x192.png     # Android icon
├── favicon-512x512.png     # Large icon
├── apple-touch-icon.png    # iOS icon (180x180)
├── house-icon.svg          # Source SVG icon
├── README.md               # This file
└── CUSTOMIZATION_GUIDE.md  # Detailed guide
```

## 🌐 Deployment

### GitHub Pages
1. Create a new repository
2. Upload all files
3. Go to Settings > Pages
4. Select main branch
5. Save and wait for deployment

### Netlify
1. Drag and drop the `MonmouthFiles` folder to [app.netlify.com](https://app.netlify.com)
2. Your site will be live instantly
3. Custom domain available in settings

### Vercel
1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` in the folder
3. Follow prompts
4. Site deployed!

## 🔍 Browser Compatibility

Tested and working on:
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 🐛 Troubleshooting

**Issue:** Pages not switching when clicking nav links
- **Solution:** Clear browser cache and hard refresh (Ctrl+Shift+R)

**Issue:** Passwords not working
- **Solution:** Passwords are case-sensitive, check for typos

**Issue:** Animations too fast/slow
- **Solution:** Adjust duration values in CSS (see Customization Guide)

**Issue:** Mobile layout broken
- **Solution:** Check that viewport meta tag is present in `<head>`

**Issue:** Favicons not showing
- **Solution:** Clear browser cache, favicons can take time to update

## 📚 Resources

- **HTML/CSS:** [MDN Web Docs](https://developer.mozilla.org)
- **JavaScript:** [JavaScript.info](https://javascript.info)
- **Colors:** [Coolors](https://coolors.co)
- **Fonts:** [Google Fonts](https://fonts.google.com)
- **Icons:** [Font Awesome](https://fontawesome.com)

## 📄 License

Free to use and modify for personal and team projects.

## 🤝 Contributing

This is a standalone project designed for team use. Feel free to fork and customize for your own needs!

## 📧 Support

For questions or issues:
- Check the Customization Guide
- Review the Troubleshooting section
- Inspect browser console for errors (F12)

## ⚡ Performance Tips

1. **Optimize Images:** Compress any uploaded images
2. **Minimize JavaScript:** Remove unused polls/bulletin items
3. **Cache Static Assets:** Use browser caching for faster loads
4. **CDN for Fonts:** Google Fonts already uses CDN

## 🎯 Future Enhancements

Ideas for expanding the website:
- [ ] Backend database for persistent data
- [ ] User authentication system
- [ ] Image upload for player photos
- [ ] Calendar integration
- [ ] Email notifications for polls
- [ ] Dark mode toggle
- [ ] Print-friendly views

---

**Created with ❤️ for team collaboration**

Signed, Advi
