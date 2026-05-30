# Meridian Calendar

<img width="2000" height="2000" alt="meridianlogo" src="https://github.com/user-attachments/assets/886b5a66-752d-48e9-a88c-2253d7ccff83" />


> A premium, feature-rich calendar application with an elegant dark-themed UI, built with vanilla HTML, CSS, and JavaScript.

## ✨ Features

### 📅 Multiple Views
- **Month View** - Classic monthly calendar with event overview
- **Week View** - Detailed hourly schedule for focused planning
- **List View** - Chronological event listing for quick scanning

### 🎯 Event Management
- Create events with custom titles and durations
- Add optional notes and time specifications
- Three styling options: Solid, Outline, and Subtle
- One-click event deletion
- All-day event support
- Existing events display in modal for easy reference

### 🔍 Smart Navigation & Search
- **Mini Calendar** - Quick month navigation in sidebar
- **Search Functionality** - Real-time event search by title or notes
- **Upcoming Events Agenda** - Next 5 upcoming events at a glance
- **Date Jumping** - Click any date in mini calendar to jump

### 📊 Statistics Dashboard
- Events this month
- Total events count
- Busiest day indicator
- This week's event count

### ⌨️ Keyboard Shortcuts
| Shortcut | Action |
|----------|--------|
| `M` | Switch to Month view |
| `W` | Switch to Week view |
| `L` | Switch to List view |
| `T` | Jump to today |
| `N` | Create new event |
| `/` | Focus search |
| `← →` | Navigate prev/next period |

### 🎨 Design Highlights
- **Premium Dark Theme** - Sophisticated dark color palette with carefully chosen contrasts
- **Typography** - DM Serif Display for headings, DM Mono for content
- **Responsive Layout** - Adapts to various screen sizes
- **Smooth Animations** - Elegant transitions and modal effects
- **Accessibility** - Clear button states and visual hierarchy

## 🚀 Quick Start

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/meridian-calendar.git
cd meridian-calendar
```

2. Open `index.html` in your browser:
```bash
# Using Python
python -m http.server 8000

# Or just open directly
open index.html
```

3. Done! The calendar is ready to use. Events are stored in browser's memory (session-based).

## 📖 Usage

### Creating an Event
1. Click the **"+ New Event"** button in the header, or press `N`
2. Click on any date in the calendar
3. Fill in event details:
   - Title (required)
   - Time (optional)
   - Duration (default: 1 hour)
   - Style (Solid/Outline/Subtle)
   - Notes (optional)
4. Click **"Save Event"** to confirm

### Viewing Events
- **Month View**: See all events for each day in a grid format
- **Week View**: Hourly breakdown with visual event placement
- **List View**: Chronological list of all upcoming events

### Searching Events
1. Press `/` or click the search box in the sidebar
2. Type event title or keywords from notes
3. Results appear instantly below the search box
4. Click any result to open the event modal

### Deleting Events
1. Open the event modal by clicking on an event
2. Click the `×` button next to the event
3. Event is instantly removed

### Navigating
- Use **← →** buttons to move between months/weeks
- Click **"Today"** button to jump to current date
- Use arrow keys `← →` as keyboard shortcut
- Click dates in the mini calendar for quick jumps

## 🛠️ Customization

### Modifying Colors
Edit the CSS variables in the `<style>` section:

```css
:root {
  --bg:       #0c0c0c;      /* Main background */
  --bg2:      #141414;      /* Secondary background */
  --border:   #2a2a2a;      /* Border color */
  --text:     #d8d6d0;      /* Text color */
  --bright:   #f2f0ea;      /* Bright text */
  --white:    #f5f4f0;      /* Accent white */
}
```

### Changing Fonts
Modify the font imports and CSS variables:

```css
:root {
  --serif: 'DM Serif Display', Georgia, serif;
  --mono:  'DM Mono', 'Courier New', monospace;
}
```

### Adjusting Event Duration Options
Find the `evtDur` select element and modify options:

```html
<select class="form-input" id="evtDur">
  <option value="0">All day</option>
  <option value="30">30 min</option>
  <option value="60" selected>1 hour</option>
  <!-- Add more options as needed -->
</select>
```

## 💾 Data Persistence

Currently, Meridian stores events in the browser's memory. To add persistent storage:

### Using Local Storage
```javascript
// Save events
localStorage.setItem('meridian_events', JSON.stringify(events));

// Load events
const savedEvents = JSON.parse(localStorage.getItem('meridian_events') || '{}');
```

### Using IndexedDB or Backend API
Modify the save/load functions to connect to your database.

## 📦 File Structure

```
meridian-calendar/
├── index.html          # Main application file
├── meridianlogo.png    # Logo asset
└── README.md          # This file
```

## 🎯 Project Structure (Code Overview)

- **HTML**: Semantic markup with modal overlay for event creation
- **CSS**: Custom properties, flexbox/grid layouts, smooth animations
- **JavaScript**: Vanilla JS (no dependencies)
  - Date calculations and formatting
  - Event CRUD operations
  - View switching and rendering
  - Keyboard event handling
  - Search and filter logic

## 🌟 Features in Detail

### Month View
- 7-day week grid layout
- Visual distinction for weekends
- Current day highlighting
- Event pill display with overflow indicators
- Click any cell to add/view events

### Week View
- Hourly time slots (24 hours)
- 7-column layout for days
- Positioned events showing duration
- Time labels on the left
- Current day highlighted in header

### List View
- Grouped by month and day
- Color-coded event dots matching event type
- Time information display
- Quick delete buttons
- Clean, scannable layout

## 🔧 Browser Support

- ✅ Chrome/Chromium (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)

Requires modern browser with ES6 JavaScript support.

## 📝 Sample Data

Meridian comes pre-populated with sample events for the current month to demonstrate functionality. These can be removed or customized in the seeder function:

```javascript
const seeder=[
  [`${y}-${m}-03`,'Team standup','09:00','solid'],
  // Add or remove sample events here
];
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 💬 Support & Feedback

For issues, feature requests, or feedback:
- Open an issue on GitHub
- Contact: [your-email@example.com]
- Website: [your-website.com]

## 🎨 Design Credits

- **Typography**: [Google Fonts](https://fonts.google.com/) - DM Serif Display, DM Mono
- **Icons**: Custom SVG icons for calendar, navigation, and controls
- **Color Palette**: Premium dark theme design

## 🚀 Future Roadmap

- [ ] Local storage persistence
- [ ] Cloud sync with Firebase
- [ ] Event categories and color coding
- [ ] Recurring events
- [ ] Event reminders/notifications
- [ ] Multi-user support
- [ ] Calendar sharing
- [ ] Export to iCal format
- [ ] Dark/Light theme toggle
- [ ] Mobile app version

## 📸 Screenshots

### Month View
Clean, organized calendar with all events visible at a glance.

### Week View
Detailed hourly breakdown perfect for scheduling.

### List View
Streamlined event list for quick event overview.

---

**Made with ❤️ for better productivity**

Meridian Calendar © 2024. All rights reserved.
