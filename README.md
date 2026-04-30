# Visual Dial 2.0

An animated visual bookmarks panel Firefox extension that replaces your new tab page with an elegant speed dial dashboard.

## Features

- 🎨 **Visual Bookmarks** — Display your bookmarks as attractive card tiles with custom images
- 📁 **Folder Organization** — Organize bookmarks into folders for better management
- 🔍 **Search Functionality** — Quickly search through your bookmarks
- 🎯 **Multiple Search Engines** — Choose from Google, Bing, DuckDuckGo, Perplexity, ChatGPT Search, and more
- 🖼️ **Custom Backgrounds** — Set custom or predefined background images for your dashboard
- 📱 **Responsive Design** — Clean, modern UI that works seamlessly
- ⚙️ **Settings Panel** — Easy-to-use settings for customization
- 🌐 **Favicon Support** — Automatically fetch favicons for bookmarks

## Installation

1. Clone or download this repository
2. Open Firefox and navigate to `about:debugging`
3. Click "This Firefox" in the left sidebar
4. Click "Load Temporary Add-on"
5. Navigate to the extension folder and select `manifest.json`

For permanent installation, you can package the extension as an .xpi file.

## Project Structure

```
visual-dial-2.0/
├── manifest.json           # Extension manifest (Firefox)
├── db.js                   # IndexedDB database management
├── main.css                # Global styles
├── README.md              # This file
│
├── dashboard/             # New Tab dashboard
│   ├── dashboard.html     # Dashboard HTML layout
│   ├── dashboard.js       # Dashboard logic and event handlers
│   └── dashboard.css      # Dashboard-specific styles
│
├── popup/                 # Extension popup
│   ├── popup.html        # Popup HTML
│   ├── popup.js          # Popup logic
│   └── popup.css         # Popup styles
│
├── icons/                # Extension icons
│   └── iconVisual.ico    # Extension icon
│
└── backgrounds/          # Background image assets
```

## Database Schema

The extension uses IndexedDB to store bookmarks locally. Each bookmark record contains:

```javascript
{
  id        : string   // Unique identifier
  folderId  : string   // Parent folder ID (or 'root')
  folderName: string   // Parent folder name (cached)
  title     : string   // Bookmark title
  url       : string   // URL (empty for folders)
  image     : string   // Base64 PNG image (230x135) or empty
  order     : number   // Sort order index
  isFolder  : boolean  // Whether this is a folder
}
```

## Features Overview

### Dashboard
- Displays all bookmarks as a responsive grid
- Click on a bookmark to navigate to the URL
- Right-click or use edit mode to modify bookmarks
- Drag and drop to reorder bookmarks and folders

### Settings Panel
- **Background**: Choose from predefined backgrounds or upload custom images
- **Search Engine**: Select your preferred search engine for the search bar
- **Info**: Display extension information

### Search
- Type in the search box to filter bookmarks
- Supports fuzzy search across bookmark titles

### Edit Mode
- Edit bookmark titles, URLs, and images
- Add favicon automatically from the website
- Delete bookmarks and folders
- Create new folders

## Permissions

The extension requests the following permissions:

- `bookmarks` — Access browser bookmarks
- `storage` — Store user preferences and data locally
- `tabs` — Access tab information
- `activeTab` — Access the current active tab
- `https://api.microlink.io/*` — Fetch page previews (optional feature)
- `https://www.google.com/s2/favicons*` — Fetch website favicons

## Browser Support

- **Firefox** — Full support (Manifest V3)
- Requires Firefox 109+

## Technical Details

- **Storage**: Uses IndexedDB for persistent data storage
- **Styling**: Pure CSS with Font Awesome icons
- **API**: Microlink API for enhanced bookmark previews
- **No External Dependencies**: Minimal use of external libraries

## Usage Tips

1. **Add Bookmarks**: Use your browser's bookmark manager to create bookmarks
2. **Organize**: Create folders to group related bookmarks
3. **Customize**: Open settings to change background and search engine
4. **Search**: Use the search bar to quickly find bookmarks
5. **Edit**: Right-click any bookmark to edit its details

## Troubleshooting

- **Bookmarks not showing**: Try refreshing the page or reopening Firefox
- **Images not loading**: Check that image URLs are valid and accessible
- **Settings not saving**: Clear your browser cache and try again

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is created by Synex. All rights reserved.

## Version

Current version: **2.0**

---

Made with ❤️ for Firefox users

