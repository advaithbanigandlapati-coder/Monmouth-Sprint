# Monmouth Sprint Website - Customization Guide

## 📋 Table of Contents
1. [Changing Colors](#changing-colors)
2. [Adding/Editing Players](#addingediting-players)
3. [Managing News Articles](#managing-news-articles)
4. [Updating Passwords](#updating-passwords)
5. [Customizing Fonts](#customizing-fonts)
6. [Adjusting Animations](#adjusting-animations)
7. [Modifying the Bulletin Board](#modifying-the-bulletin-board)
8. [Contact Information](#contact-information)

---

## 🎨 Changing Colors

The warm color palette is defined using CSS variables at the top of the `<style>` section. Find this block:

```css
:root {
    --sunset-orange: #FF6B35;
    --terracotta: #D65A31;
    --warm-amber: #F7931E;
    --sand: #F4E5D3;
    --deep-sienna: #A63D29;
    --cream: #FFF8F0;
    --burnt-umber: #6B2C1F;
    --coral: #FF8B6A;
    --dark-bg: #2A1810;
}
```

**To change colors:** Simply replace the hex color codes (e.g., `#FF6B35`) with your preferred colors. You can use:
- Online color pickers (Google "color picker")
- [Coolors.co](https://coolors.co) for palette generation
- Adobe Color for professional palettes

**Example:** To make the site more blue-themed:
```css
--sunset-orange: #4A90E2;  /* Changed to blue */
--terracotta: #2C5F8D;     /* Changed to darker blue */
```

---

## 👥 Adding/Editing Players

Find the `playersData` array in the JavaScript section (near the bottom of the file). Each player follows this structure:

```javascript
{
    name: "Player Name",
    overall: 8.5,  // Out of 10
    description: "Brief description of the player's strengths and style",
    stats: {
        reflexes: 85,      // 0-100
        spikes: 90,        // 0-100
        sets: 75,          // 0-100
        bumps: 80,         // 0-100
        safety: 95,        // 0-100
        logic: 88,         // 0-100
        teamwork: 92       // 0-100
    }
}
```

### Adding a New Player:
1. Locate the `playersData` array
2. Add a comma after the last player's closing `}`
3. Copy and paste the structure above
4. Fill in your player's information

**Stat Level Breakdown:**
- 0-29: Beginner
- 30-59: Intermediate
- 60-84: Advanced
- 85-100: Expert

### Example - Adding a Player:
```javascript
const playersData = [
    // ... existing players ...
    {
        name: "Chris Anderson",
        overall: 7.5,
        description: "Rising star with incredible potential",
        stats: {
            reflexes: 78,
            spikes: 82,
            sets: 70,
            bumps: 75,
            safety: 85,
            logic: 80,
            teamwork: 88
        }
    }
];
```

---

## 📰 Managing News Articles

News articles are in the `#news` page section. Each article uses this HTML structure:

```html
<div class="news-article">
    <h2>Article Title Goes Here</h2>
    <div class="news-meta">
        <span class="news-date">Month Day, Year</span>
        <span class="news-category">Category Name</span>
    </div>
    <p>First paragraph of content...</p>
    <p>Second paragraph of content...</p>
    <p>Additional paragraphs as needed...</p>
</div>
```

### Adding a New Article:
1. Find the news section in the HTML
2. Copy an existing article structure
3. Paste it at the top (for newest) or bottom (for oldest)
4. Update the title, date, category, and content

### Suggested Categories:
- Tournament
- Schedule
- Player Feature
- Facility Update
- Community
- Achievement
- Training

---

## 🔒 Updating Passwords

### Files Page Password (Currently: RishuNoTishu)

Find the `unlockFiles()` function:
```javascript
function unlockFiles() {
    const password = document.getElementById('filesPassword').value;
    const errorElement = document.getElementById('filesError');
    
    if (password === 'RishuNoTishu') {  // ← CHANGE THIS
        // ... rest of code
    }
}
```

Change `'RishuNoTishu'` to your desired password.

### Bulletin Board Password (Currently: Swaydih)

Find the `unlockBulletin()` function:
```javascript
function unlockBulletin() {
    const password = document.getElementById('bulletinPassword').value;
    const errorElement = document.getElementById('bulletinError');
    
    if (password === 'Swaydih') {  // ← CHANGE THIS
        // ... rest of code
    }
}
```

Change `'Swaydih'` to your desired password.

**Security Note:** These passwords are visible in the page source code. For real security, you would need a backend server. This is suitable for basic access control among team members.

---

## ✨ Customizing Fonts

The site currently uses:
- **Bebas Neue** for headings (bold, display font)
- **Inter** for body text (clean, readable)

### To Change Fonts:

1. **Find a font on Google Fonts:**
   - Visit [fonts.google.com](https://fonts.google.com)
   - Select your fonts
   - Copy the `<link>` code

2. **Replace the font import in the `<head>` section:**
```html
<link href="https://fonts.googleapis.com/css2?family=YourFont:wght@400;700&display=swap" rel="stylesheet">
```

3. **Update the CSS:**
```css
/* For headings */
.hero-title, .page-title, .player-name {
    font-family: 'YourDisplayFont', sans-serif;
}

/* For body text */
body, p, input, textarea {
    font-family: 'YourBodyFont', sans-serif;
}
```

### Popular Font Combinations:
- **Modern/Tech:** Montserrat + Open Sans
- **Bold/Athletic:** Oswald + Roboto
- **Classic/Elegant:** Playfair Display + Lato
- **Fun/Energetic:** Fredoka One + Nunito

---

## 🎬 Adjusting Animations

Animation speeds are controlled by duration values in transitions and animations.

### Common Animation Properties:

```css
/* Transitions (hover effects, etc.) */
transition: all 0.3s ease;
         /* property | duration | timing */

/* Animations (page loads, etc.) */
animation: fadeIn 0.6s ease;
        /* name | duration | timing */
```

### To Slow Down Animations:
Increase the duration (in seconds):
```css
transition: all 0.6s ease;  /* Was 0.3s, now slower */
animation: fadeIn 1.2s ease; /* Was 0.6s, now slower */
```

### To Speed Up Animations:
Decrease the duration:
```css
transition: all 0.15s ease;  /* Was 0.3s, now faster */
animation: fadeIn 0.3s ease;  /* Was 0.6s, now faster */
```

### To Disable Animations:
Comment out or remove animation lines:
```css
/* animation: fadeIn 0.6s ease; */  ← Now disabled
```

---

## 📌 Modifying the Bulletin Board

The bulletin board items are stored in the `bulletinItems` array:

```javascript
const bulletinItems = [
    { date: 'Feb 1, 2026', text: 'Your announcement text here' },
    { date: 'Jan 30, 2026', text: 'Another announcement' },
    // Add more items...
];
```

### Pre-loading Announcements:
Add items to this array in the JavaScript section. The most recent items should be at the top.

**Example:**
```javascript
const bulletinItems = [
    { 
        date: 'Feb 5, 2026', 
        text: 'Important: Team photos this Friday at 3 PM. Wear your uniforms!' 
    },
    { 
        date: 'Feb 3, 2026', 
        text: 'Pizza party after Saturday\'s game - everyone invited!' 
    }
];
```

---

## 📧 Contact Information

To update the contact page behavior, modify the `handleContactSubmit()` function:

```javascript
function handleContactSubmit(event) {
    event.preventDefault();
    alert('Thank you for your message! We\'ll get back to you as soon as possible.');
    event.target.reset();
}
```

### To Send to a Real Email:
You'll need to integrate with a service like:
- **Formspree** (easiest, free tier available)
- **EmailJS** (free tier, client-side)
- **Custom backend** (requires server programming)

**Example with Formspree:**
1. Sign up at [formspree.io](https://formspree.io)
2. Create a form and get your form ID
3. Update the form tag:
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

---

## 🔧 Quick Reference

### File Structure:
- Everything is in one HTML file
- CSS is in the `<style>` section
- JavaScript is in the `<script>` section at the bottom
- Pages are `<div>` elements with class="page"

### Making Changes:
1. Open the HTML file in a text editor (VS Code, Notepad++, etc.)
2. Find the section you want to modify
3. Make your changes
4. Save the file
5. Open in a web browser to test

### Testing Changes:
- Use Chrome/Firefox DevTools (F12) to debug
- Hard refresh (Ctrl+Shift+R) to see CSS changes
- Check browser console for JavaScript errors

---

## 🆘 Troubleshooting

**Problem:** Colors aren't changing
- **Solution:** Make sure you're editing the `:root` variables, not individual color values

**Problem:** Player cards not showing
- **Solution:** Check that your JavaScript has proper syntax (commas between objects, matching brackets)

**Problem:** Password not working
- **Solution:** Passwords are case-sensitive; check for extra spaces

**Problem:** Animations too fast/slow
- **Solution:** Adjust the decimal values (0.3s, 0.6s, etc.)

**Problem:** Layout broken on mobile
- **Solution:** The responsive design should handle this, but check the `@media` queries if needed

---

## 📞 Need More Help?

- **HTML/CSS Basics:** [MDN Web Docs](https://developer.mozilla.org)
- **JavaScript Help:** [JavaScript.info](https://javascript.info)
- **Design Inspiration:** [Dribbble](https://dribbble.com), [Behance](https://behance.net)
- **Color Tools:** [Coolors](https://coolors.co), [Adobe Color](https://color.adobe.com)

---

**Remember:** Always make a backup copy of your HTML file before making major changes!

**Pro Tip:** Use browser DevTools to test changes live before editing the actual file.

---

Signed, Advi
