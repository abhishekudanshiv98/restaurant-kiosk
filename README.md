# Hotel Chul - Guest Feedback Kiosk

A beautiful, fine-dining iPad kiosk with an auto-rotating slideshow and embedded Google Form for guest feedback.

## Setup

### 1. Add Your Dish Photos

Place your restaurant photos in the `images/` folder:

```
images/
├── dish1.jpg
├── dish2.jpg
├── dish3.jpg
├── dish4.jpg
└── ... (up to dish8.jpg)
```

**Photo Requirements:**
- **Format:** JPG or PNG
- **Size:** Landscape orientation (1200px+ wide)
- **File size:** Under 2MB per image
- **Quantity:** 3-8 photos work best

**What to shoot:**
- Hero dish photos 🍽️
- Ambiance/restaurant interior 🕯️
- Dessert closeups 🍮
- Happy guests (with permission) 👥

### 2. Deploy to GitHub Pages

#### Step 1: Push to GitHub

```bash
cd restaurant-kiosk
git add .
git commit -m "Initial kiosk setup with Hotel Chul branding"
git push origin main
```

#### Step 2: Enable GitHub Pages

1. Go to your GitHub repo → **Settings**
2. Navigate to **Pages** (left sidebar)
3. Set **Source** to `gh-pages` branch
4. Your kiosk will be live at: `https://yourusername.github.io/restaurant-kiosk`

#### Step 3: Open on iPad

1. Open Safari on iPad
2. Visit your GitHub Pages URL
3. **Settings → Accessibility → Guided Access → Enable**
4. Triple-click home button to lock it
5. Done! 🎉

### 3. CI/CD Pipeline

Every time you push a change, GitHub Actions automatically:
- ✅ Builds your site
- ✅ Deploys to GitHub Pages
- ✅ Live in ~30 seconds

No manual steps needed after the initial setup!

## How It Works

**Media Carousel (Images + Videos):**
- 🖼️ **Images** auto-rotate every 5 seconds
- 🎬 **Videos** auto-play when they appear, play fully, then advance
- Sequential playback based on filename order (use numbering: 01-, 02-, etc.)
- Mix images and videos - they all rotate seamlessly

**iOS Video Autoplay (Fixed ✅):**
- Videos require user gesture first (tap screen for fullscreen)
- Once you tap the screen, videos autoplay automatically on iPad
- No manual clicking required - tap once, then sit back! 🎉
- Works on Chrome, Safari, all browsers

**Customer Journey:**
1. iPad displays rotating slideshow of dishes (5 sec per image, videos play fully)
2. Videos autoplay automatically after first tap
3. Customer taps "📝 Share Your Feedback" button on slideshow background
3. Google Form opens in fullscreen
4. Customer completes 6 questions (~1 min):
   - Overall experience rating ⭐
   - Food quality rating ⭐
   - Staff & service rating ⭐
   - How did you hear about us? 
   - Open feedback 💬
   - Name & email (optional)
5. Submits → "Thank You" message (2.5 sec)
6. Auto-returns to slideshow ✨

## Customization

### Change Colors
Edit the CSS in `index.html`:
```css
.header {
  background: linear-gradient(90deg, #6b1f2a 0%, #8b3a3a 100%); /* Burgundy */
}
```

**Color Reference:**
- Burgundy: `#6b1f2a` (dark), `#8b3a3a` (lighter)
- Gold: `#d4af37` (primary), `#c9a961` (accent)

### Change Slide Duration
In `index.html`, find this line:
```javascript
setInterval(() => {
  // ... code ...
}, 5000); // Change 5000 to milliseconds (5000 = 5 seconds)
```

### Update Google Form URL
Replace the form URL in `index.html`:
```html
<iframe src="YOUR_NEW_FORM_URL?embedded=true" ...></iframe>
```

## Troubleshooting

**Images not showing?**
- Check image filenames match `dish1.jpg`, `dish2.jpg`, etc.
- Ensure they're in the `images/` folder
- Try refreshing the page (Cmd+R on Mac, Ctrl+R on Windows)

**Form not submitting?**
- Check your internet connection on iPad
- Make sure Google Form is published (not draft)

**GitHub Pages not updating?**
- Check Actions tab in GitHub repo for build status
- Wait 1-2 minutes, then force refresh (Shift+Cmd+R)

## Support

For issues with the kiosk setup, check your repo's GitHub Actions tab for build logs.

---

**Restaurant:** Hotel Chul  
**Theme:** Fine Dining Elegance  
**Status:** 🟢 Live & Ready  
**Features:** 🎵 Multi-song daily shuffle, 📹 Video carousel, 📝 Guest feedback form
