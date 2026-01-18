# Ballad Health Orientation Bag Tracker

A Progressive Web App (PWA) for managing seating and bag placement during Ballad Health orientation days.

## Features

- **Smart Bag Placement**: Enter number of team members and automatically places bags in optimal order
- **Visual Seating Layout**: 4-4-2-4-4 configuration across 6 rows (108 total chairs)
- **Interactive**: Click any chair to manually toggle bag placement (for spills, broken chairs, etc.)
- **Fill Priority**: Automatically fills middle/front first, avoids right column and back row until last
- **Works Offline**: Once installed, works without internet connection
- **Mobile & Desktop**: Responsive design works on all devices

## Seating Layout

The room is arranged with 6 rows of chairs:
- Each row: 4 chairs | 4 chairs | 2 chairs | 4 chairs | 4 chairs (18 chairs per row)
- Total: 108 chairs
- Chairs numbered 1-108 (left to right, front to back)

## Fill Priority

The app automatically fills in this order:
1. **Front and middle sections first** (rows 1-5, middle tables)
2. **Expand outward** to left and right 4-chair sections
3. **Right column chairs** (chair #18, 36, 54, 72, 90)
4. **Back row last** (row 6, chairs 91-108)

This keeps team members away from your team table and the back checkout area.

## How to Use

1. **Enter the number of team members** expected
2. **Click "Place Bags"** - bags are automatically placed in optimal positions
3. **Click any chair** to manually toggle if needed (for broken chairs, spills, etc.)
4. **Click "Reset All"** to start over

## Setup Instructions for GitHub Pages

You already created the repository! Now let's upload the files:

### Step 1: Upload Files

1. In your `orientation_bag_tracker` repository on GitHub
2. Click **"uploading an existing file"** or **Add file → Upload files**
3. Drag and drop ALL files from this folder:
   - index.html
   - manifest.json
   - service-worker.js
   - apps/ folder
   - styles/ folder
   - images/ folder
4. Scroll down and click **"Commit changes"**

### Step 2: Enable GitHub Pages

1. Click the **Settings** tab
2. Click **Pages** in the left sidebar
3. Under "Source", select **main** branch
4. Make sure it says **"/ (root)"** for the folder
5. Click **Save**

### Step 3: Access Your App

Wait 1-2 minutes, then visit:
```
https://tchastain26.github.io/orientation_bag_tracker/
```

(Replace `tchastain26` with your GitHub username if different)

## Installing as PWA

### On Desktop (Chrome/Edge)
1. Visit your site
2. Look for install icon in address bar
3. Click "Install"

### On iPhone
1. Open in Safari
2. Tap Share button
3. Tap "Add to Home Screen"

### On Android
1. Open in Chrome
2. Tap menu (3 dots)
3. Tap "Add to Home Screen"

## File Structure

```
orientation_bag_tracker/
├── index.html                      # Homepage
├── manifest.json                   # PWA configuration
├── service-worker.js              # Offline functionality
├── apps/
│   └── orientation-bag-tracker.html  # Main app
├── styles/
│   └── main.css                   # Styling
└── images/
    ├── icon-192.png               # App icons
    └── icon-512.png
```

## Making Changes

If you need to modify the layout or fill priority:

1. Edit `apps/orientation-bag-tracker.html`
2. The `LAYOUT` array defines chairs per section: `[4, 4, 2, 4, 4]`
3. The `generateFillPriority()` function determines fill order
4. Commit changes to GitHub
5. Wait 1-2 minutes for deployment

## Troubleshooting

**Site not loading?**
- Wait 2-3 minutes after enabling GitHub Pages
- Try hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

**Changes not showing?**
- Hard refresh your browser
- Clear browser cache
- Update cache version in `service-worker.js` (change `v1` to `v2`)

**PWA not installing?**
- Must be accessed via HTTPS (GitHub Pages does this automatically)
- Check that manifest.json is loading
- Try Chrome DevTools → Application → Manifest

## Tips for Orientation Day

1. **Before the event**: 
   - Open the app and enter expected number
   - Screenshot the layout for your team
   
2. **During the event**:
   - Use the app on a tablet at your team table
   - Toggle chairs as needed for last-minute changes
   
3. **After the event**:
   - Click Reset All for next session

## Browser Support

Works on:
- Chrome (desktop & mobile)
- Safari (desktop & mobile)
- Edge
- Firefox
- Samsung Internet

## Questions or Issues?

The app is designed to work standalone without additional support, but if you need to modify functionality, the code is well-commented and easy to understand.

---

**Ready to use!** Just upload these files to your GitHub repository and enable GitHub Pages. Your team will be able to access it from anywhere!
