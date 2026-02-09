
# 🎯 Habit Tracker - Beginner-Friendly Version

A complete, modern Habit Tracker website built with **HTML, CSS, and JavaScript** (no frameworks!). Perfect for beginners learning web development.

![Version](https://img.shields.io/badge/Version-1.0-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Beginner Friendly](https://img.shields.io/badge/Beginner-Friendly-yellow)

## 📸 Screenshots

### Login Page
Simple and clean authentication interface

### Dashboard
Track your daily habits with visual progress indicators

### Progress & Analytics
View your weekly progress and completion rates

### Calendar View
Month view with color-coded completion status

## ✨ Features

### 🔐 Authentication
- Email & Password Login/Signup
- Firebase Authentication support
- Demo mode with localStorage (works without Firebase)
- Persistent login sessions

### 📊 Dashboard
- Today's habit completion counter
- Current streak tracker 🔥
- Total habits overview
- Quick habit marking

### ✅ Habit Management
- Add new habits with:
  - Custom names
  - Categories (Health, Fitness, Study, etc.)
  - Frequency (Daily/Weekly)
  - Optional reminder times
- Edit existing habits
- Delete habits
- Mark habits as complete/incomplete

### 📈 Progress Tracking
- Longest streak counter
- Overall completion rate
- Total completions
- Weekly progress chart
- Individual habit breakdown

### 📅 Calendar View
- Monthly calendar display
- Color-coded completion status:
  - 🟢 Green = All habits completed
  - 🟠 Orange = Some habits completed
  - ⚪ Gray = No habits completed
- Navigate between months

### 🌙 Dark Mode
- Toggle between light and dark themes
- Preference saved to localStorage

### 💾 Data Persistence
- All habits saved to localStorage
- Data persists across sessions
- Per-user data storage

## 📁 File Structure

```
habit-tracker/
│
├── index.html          # Main HTML file (all pages in one)
├── style.css           # Complete CSS with dark mode
├── script.js           # Main JavaScript functionality
├── firebase.js         # Firebase authentication
└── README.md           # Documentation
```

## 🚀 How to Run

### Option 1: Open Directly (Recommended for Beginners)

1. **Download all files** to a folder on your computer
2. **Double-click** `index.html`
3. The app opens in your default browser
4. **Done!** No server needed!

### Option 2: Using VS Code Live Server

1. Open folder in **VS Code**
2. Install **Live Server** extension
3. Right-click `index.html`
4. Select "Open with Live Server"

### Option 3: Using Python Server

```bash
# Python 3
python -m http.server 8000

# Then open: http://localhost:8000
```

## 📖 Usage Guide

### 1️⃣ First Time Setup

1. Open the app
2. You'll see the **Login page**
3. Click **"Sign Up"** to create an account
4. Enter:
   - Your name
   - Email address
   - Password (minimum 6 characters)
5. Click **"Sign Up"**

### 2️⃣ Adding Your First Habit

1. After login, click **"+ Add Habit"** button
2. Fill in the form:
   - **Habit Name**: e.g., "Drink 8 glasses of water"
   - **Category**: Choose from dropdown
   - **Frequency**: Daily or Weekly
   - **Reminder Time**: Optional (e.g., 08:00 AM)
3. Click **"Save Habit"**

### 3️⃣ Tracking Daily Progress

1. View your habits on the dashboard
2. Click the **checkmark button** ✓ to mark complete
3. Watch your streak increase! 🔥
4. Click again to unmark if needed

### 4️⃣ Viewing Progress

1. Click the **"Progress"** tab
2. See:
   - Longest streak
   - Completion rate percentage
   - Total completions
   - Weekly chart
   - Habits breakdown

### 5️⃣ Calendar View

1. Click the **"Calendar"** tab
2. View your entire month
3. Color-coded days show completion status
4. Use arrows to navigate months

### 6️⃣ Editing or Deleting Habits

- Click **Edit** button (✏️) to modify habit
- Click **Delete** button (🗑️) to remove habit
- Confirmation prompt prevents accidents

### 7️⃣ Dark Mode

- Click the **moon icon** 🌙 in top right
- Theme switches instantly
- Preference is saved

## 🔧 How It Works (Code Explanation)

### Authentication Flow

```javascript
// 1. User enters email & password
// 2. firebase.js handles authentication
// 3. Returns user object if successful
// 4. User data stored in currentUser variable
// 5. Dashboard loads user's habits
```

### Data Storage

```javascript
// Habits stored in localStorage per user
localStorage.setItem(`habits_${userId}`, JSON.stringify(habits));

// Format: habits_[userId] = [
//   { id, name, category, frequency, completedDates, streak }
// ]
```

### Habit Structure

```javascript
{
  id: "1675234567890",           // Unique timestamp ID
  name: "Morning Exercise",       // Habit name
  category: "Fitness",            // Category
  frequency: "daily",             // daily or weekly
  reminderTime: "07:00",          // Optional
  completedDates: [               // Array of date strings
    "Sun Feb 09 2026",
    "Sat Feb 08 2026"
  ],
  streak: 5,                      // Current streak
  longestStreak: 12,              // Best streak ever
  createdAt: "2026-02-01",        // Creation date
  archived: false                 // Soft delete
}
```

## 🔥 Firebase Setup (Optional)

The app works **without Firebase** using demo mode. To enable real Firebase authentication:

### Step 1: Create Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Add Project"
3. Name it "Habit Tracker"
4. Follow setup wizard

### Step 2: Enable Authentication

1. In Firebase Console, go to **Authentication**
2. Click "Get Started"
3. Enable **Email/Password** sign-in method

### Step 3: Get Configuration

1. Go to **Project Settings** (gear icon)
2. Scroll to "Your apps"
3. Click **Web** icon (</>) to add web app
4. Copy the `firebaseConfig` object

### Step 4: Update firebase.js

Replace the config in `firebase.js`:

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "your-app.firebaseapp.com",
    projectId: "your-project-id",
    storageBucket: "your-app.appspot.com",
    messagingSenderId: "123456789",
    appId: "your-app-id"
};
```

### Step 5: Test

- Refresh the app
- Sign up with a real email
- Firebase authentication is now active!

## 📚 Learning Resources

### HTML Concepts Used
- Semantic HTML5 elements
- Forms and inputs
- Data attributes
- Modal dialogs

### CSS Concepts Used
- CSS Variables (Custom Properties)
- Flexbox & Grid layouts
- Transitions & Animations
- Media queries (Responsive design)
- Dark mode with class toggle

### JavaScript Concepts Used
- DOM manipulation
- Event listeners
- LocalStorage API
- Array methods (map, filter, reduce)
- Date manipulation
- Async/Await (for Firebase)
- Template literals

## 🎨 Customization Guide

### Change Colors

Edit CSS variables in `style.css`:

```css
:root {
    --primary-color: #6366f1;    /* Change to your color */
    --secondary-color: #8b5cf6;  /* Gradient color */
    --success-color: #10b981;    /* Success green */
}
```

### Add New Categories

In `script.js`, update the category emoji function:

```javascript
function getCategoryEmoji(category) {
    const emojis = {
        'Health': '💊',
        'Fitness': '💪',
        'Study': '📚',
        'YourCategory': '🎨'  // Add your category
    };
    return emojis[category] || '📌';
}
```

And update the HTML select options in `index.html`:

```html
<option value="YourCategory">🎨 Your Category</option>
```

### Change Reminder Format

In `index.html`, modify the time input:

```html
<input type="time" id="reminderTime" step="900">
<!-- step="900" = 15 minute intervals -->
```

## 🐛 Troubleshooting

### Habits not saving?

- Check browser console (F12) for errors
- Ensure localStorage is enabled
- Try clearing browser cache

### Can't login?

- Check that email and password are correct
- Password must be at least 6 characters
- In demo mode, any valid email works

### Dark mode not working?

- Check if localStorage is enabled
- Try refreshing the page
- Clear browser cache

### Calendar not showing?

- Ensure you have at least one habit
- Try switching to another tab and back
- Check browser console for errors

## 🌟 Future Enhancements

Ideas for expanding the project:

- [ ] Add habit notes/journal entries
- [ ] Export data to CSV
- [ ] Habit sharing with friends
- [ ] Push notifications
- [ ] Habit templates
- [ ] Goals and milestones
- [ ] Mobile app version
- [ ] Backend API integration
- [ ] Social features
- [ ] Gamification (badges, levels)

## 💡 Tips for Beginners

1. **Start Simple**: Add 2-3 habits first, don't overwhelm yourself
2. **Be Consistent**: Check in daily, even if just to mark habits
3. **Celebrate Streaks**: Every 7-day streak is a win! 🎉
4. **Don't Break the Chain**: Use the calendar to visualize consistency
5. **Adjust as Needed**: Edit or delete habits that don't work for you

## 🤝 Contributing

This is a learning project! Feel free to:

- Report bugs
- Suggest features
- Submit improvements
- Share your customizations

## 📄 License

MIT License - Feel free to use for personal or educational purposes

## 🙏 Acknowledgments

- Font Awesome for icons
- Firebase for authentication
- Modern CSS techniques
- Inspired by habit tracking apps like Habitica, Streaks, and Loop

## 📞 Support

Having issues? 

1. Check this README
2. Review code comments
3. Check browser console (F12)
4. Try demo mode first

---

**Built with ❤️ for learning web development**

*"We are what we repeatedly do. Excellence, then, is not an act, but a habit." - Aristotle*

---

## 🎓 Code Breakdown for Beginners

### How the App Works

```
1. Page Loads (index.html)
   ↓
2. JavaScript Runs (script.js)
   ↓
3. Check if User is Logged In
   ↓
4. If YES → Show Dashboard
   If NO  → Show Login
   ↓
5. User Interacts (clicks buttons)
   ↓
6. JavaScript Updates UI
   ↓
7. Data Saved to localStorage
   ↓
8. UI Refreshes to show changes
```

### Key Functions Explained

**`addHabit()`**
- Creates new habit object
- Adds to habits array
- Saves to localStorage
- Updates UI

**`toggleHabit()`**
- Finds habit by ID
- Adds/removes today's date
- Updates streak counter
- Saves changes

**`renderHabits()`**
- Loops through habits array
- Creates HTML for each habit
- Inserts into page

**`toggleDarkMode()`**
- Adds/removes 'dark-mode' class
- Changes CSS variables
- Saves preference

This is a complete, working habit tracker! Perfect for learning or daily use. 🚀
