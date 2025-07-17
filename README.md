# RENEC - Estándares de Competencia

A modern, responsive web application for visualizing and exploring Mexican competency standards (Estándares de Competencia) from RENEC (Registro Nacional de Estándares de Competencia).

## Features

### 🎨 Modern Design
- **Neobrutalist UI**: Bold, modern design with strong borders and shadows
- **Dark/Light Theme**: Auto-switching based on system preference with manual override
- **Responsive Layout**: Works seamlessly on desktop, tablet, and mobile devices
- **Smooth Animations**: Subtle transitions and hover effects for enhanced user experience

### 🔍 Powerful Search & Filtering
- **Real-time Search**: Instant search across codes, titles, committees, and sectors
- **Advanced Filters**: Filter by level, committee, and productive sector
- **Smart Sorting**: Sort by code (A-Z, Z-A) or level (low-high, high-low)
- **Random Shuffle**: Discover standards randomly
- **Filter Counter**: Visual indicator of active filters

### 📊 Flexible Display Options
- **Grid View**: Card-based layout for browsing
- **List View**: Compact list format for quick scanning
- **Pagination**: Efficient navigation through large datasets (12 items per page)
- **Results Counter**: Shows current results vs total available

### 🌐 Internationalization
- **Bilingual Support**: Spanish (ES) and English (EN)
- **Easy Language Switching**: Toggle between languages instantly
- **Localized Content**: All UI elements and messages are fully translated

## Technical Stack

- **Frontend**: Vanilla HTML, CSS, and JavaScript
- **Styling**: Tailwind CSS via CDN
- **Fonts**: Inter (UI) and Space Mono (monospace) from Google Fonts
- **Icons**: Bootstrap Icons (SVG)
- **Data**: JSON file (`renec.json`) containing competency standards

## Project Structure

```
renec-website/
├── index.html          # Main application file
├── renec.json          # Competency standards data
└── README.md           # This file
```

## Data Format

The application expects a JSON file with the following structure:

```json
[
  {
    "Código": "EC0305",
    "Título": "Realizar soldadura con electrodos revestidos...",
    "Nivel": 2,
    "Comité": "Comité de Normalización de la Industria...",
    "Sector Productivo": "Industria Manufacturera"
  }
]
```

### Required Fields
- `Código`: Unique competency standard code
- `Título`: Full title of the standard
- `Nivel`: Competency level (integer)
- `Comité`: Normalizing committee name
- `Sector Productivo`: Productive sector classification

## Setup and Installation

1. **Clone or Download**: Get the project files
2. **Data File**: Ensure `renec.json` is in the same directory as `index.html`
3. **Web Server**: Serve the files through a web server (required for JSON loading)

### Local Development

```bash
# Using Python (if installed)
python -m http.server 8000

# Using Node.js (if installed)
npx http-server

# Using PHP (if installed)
php -S localhost:8000
```

Then visit `http://localhost:8000` in your browser.

## Features in Detail

### Search Functionality
- **Normalized Search**: Ignores accents and case differences
- **Multi-field Search**: Searches across all relevant fields
- **Real-time Results**: 300ms debounced search for optimal performance

### Filtering System
- **Level Filter**: Filter by competency level (1-5)
- **Committee Filter**: Filter by normalizing committee
- **Sector Filter**: Filter by productive sector
- **Combined Filters**: All filters work together seamlessly

### Theme System
- **Auto Mode**: Follows system dark/light preference
- **Manual Override**: Force light or dark mode
- **Persistent**: Remembers user preference in localStorage
- **Smooth Transitions**: Animated theme switching

### Responsive Design
- **Mobile-First**: Optimized for mobile devices
- **Breakpoints**: 
  - Mobile: < 768px
  - Tablet: 768px - 1024px
  - Desktop: > 1024px
- **Flexible Layouts**: Grid and list views adapt to screen size

## Browser Support

- ✅ Chrome/Chromium (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ⚠️ Internet Explorer (not supported)

## Performance Considerations

- **Efficient Rendering**: Only renders visible items with pagination
- **Debounced Search**: Prevents excessive filtering during typing
- **Minimal Dependencies**: Uses CDN resources for faster loading
- **Optimized Sorting**: Efficient sorting algorithms for large datasets

## Customization

### Styling
The CSS uses custom properties for easy theming:

```css
:root {
  --bg-light: #f5f5f4;
  --text-light: #1c1917;
  --accent-light: #3b82f6;
  --border-light: #1c1917;
  /* ... */
}
```

### Configuration
Key configuration options in the JavaScript:

```javascript
const itemsPerPage = 12;        // Items per page
const searchTimeout = 300;      // Search debounce time (ms)
const currentLang = 'es';       // Default language
const currentTheme = 'auto';    // Default theme
```

## Data Sources

All competency standards data belongs to **RENEC** (Registro Nacional de Estándares de Competencia). This website is a visualization tool and does not claim ownership of the data.

## Contributing

This is a standalone visualization tool. To contribute:

1. Fork the repository
2. Make your changes
3. Test thoroughly across browsers
4. Submit a pull request

## License

This project is for educational and visualization purposes. The competency standards data remains the property of RENEC.

## Support

For issues or questions about the website functionality, please check:
- Browser console for JavaScript errors
- Network tab for failed resource loading
- Ensure `renec.json` is accessible and properly formatted

---

*Website created for visualizing Competency Standards. All data belongs to RENEC.*
