# 🇩🇰 Danishly - Learn Danish

A modern, interactive Danish language learning web app with zero dependencies. Learn Danish through lessons, flashcards, spaced repetition, and cultural insights—all in a single HTML file.

## ✨ Features

### 📚 **Danish Learning Modules**
- Interactive lessons with Danish words/phrases and English translations
- Audio playback via ElevenLabs API (text-to-speech)
- Built-in modules: Greetings, Basic Phrases, Food, Animals
- Add custom lessons directly in the app
- Difficulty levels (beginner, intermediate)

### 🎴 **Spaced Repetition Flashcards**
- Automatically generated from lessons you've practiced
- Flip-card interface with visual feedback
- Accuracy tracking for each card
- Session-based learning with results summary

### 📊 **Learning Progress Tracking**
- All progress saved locally in browser storage (works offline)
- Module-level progress tracking
- Overall accuracy metrics
- Practice count tracking
- Reset option if needed

### 🇩🇰 **Cultural Insights Sidebar**
- Danish holidays, traditions, and customs
- Famous Danish foods and culinary traditions
- Historical facts about Denmark
- What Danes value and do
- Powered by Groq API
- Auto-refreshes hourly or on-demand

## 🚀 Quick Start

### 1. **Get API Keys** (takes 2 minutes)

#### ElevenLabs (for audio)
- Go to [elevenlabs.io](https://elevenlabs.io)
- Sign up (free tier available)
- Copy your API key from Settings → API Keys
- Choose a voice ID (default: "Rachel")

#### Groq (for cultural insights)
- Go to [console.groq.com](https://console.groq.com)
- Sign up for free (very generous rate limits)
- Create an API key in API Keys section

### 2. **Configure the App**
Open `index.html` in a text editor and paste your API keys in the CONFIG section at the top:

```javascript
const CONFIG = {
    ELEVENLABS_API_KEY: 'your_api_key_here',
    ELEVENLABS_VOICE_ID: 'Rachel', // or any other voice
    GROQ_API_KEY: 'your_api_key_here',
};
```

### 3. **Test Locally**
Simply open `index.html` in your browser (no server needed!):
```bash
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux
```

### 4. **Deploy to GitHub Pages**

#### Option A: Via GitHub Web UI (easiest)
1. Create a new repository: `Andrei11022/Danishly` (or any name)
2. Upload `index.html` to the repo
3. Go to **Settings → Pages**
4. Set source to `main` branch, root folder
5. Your app is live at `https://Andrei11022.github.io/Danishly/`

#### Option B: Via Git CLI
```bash
git init
git add index.html
git commit -m "Add Danishly app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/Danishly.git
git push -u origin main
```

Then enable Pages in repository settings (same as Option A step 3-5).

## 🎮 How to Use

### **Learning**
1. Browse lessons in the **Lessons** tab
2. Click "🔊 Listen" to hear pronunciation
3. Practice lessons by marking them correct/incorrect in flashcard sessions

### **Flashcards**
1. Go to the **Flashcards** tab
2. Click "🎴 Start Flashcard Session"
3. Flip cards to reveal answers
4. Mark as correct or incorrect
5. Get an accuracy summary

### **Track Progress**
- Switch to the **Progress** tab anytime
- See overall stats: words, learned count, accuracy
- View module-by-module breakdown

### **Add Custom Lessons**
Extend the lessons by editing the `LESSONS` object in the script, or add them through the UI (modal support).

## 📱 Browser Support

Works on all modern browsers:
- Chrome/Chromium
- Firefox
- Safari
- Edge

## 🔒 Privacy & Security

- ✅ All progress saved **locally** in browser (localStorage)
- ✅ No data sent to any server except:
  - ElevenLabs API (for audio generation)
  - Groq API (for cultural insights)
- ✅ Your API keys are **not transmitted anywhere** except to their respective APIs
- ⚠️ **Important**: Don't commit API keys to GitHub. Use GitHub Secrets if you want a private version.

### Securing Your API Keys

If sharing your GitHub repo publicly:
1. Create a separate config file: `config.js` (keep it locally)
2. Add `config.js` to `.gitignore`
3. Reference it before `index.html` loads

Example `config.js`:
```javascript
const CONFIG = {
    ELEVENLABS_API_KEY: process.env.ELEVENLABS_API_KEY || 'fallback_key',
    GROQ_API_KEY: process.env.GROQ_API_KEY || 'fallback_key',
};
```

## 🛠️ Customization

### Add More Lessons
Edit the `LESSONS` object in `index.html`:
```javascript
const LESSONS = {
    mymodule: [
        { danish: 'Word', english: 'Translation', difficulty: 'beginner' },
        // ...
    ]
};
```

### Change Colors
The app uses Danish flag colors (red #c8102e) by default. Modify in the CSS:
```css
:root {
    --primary: #c8102e;      /* Change this */
    --primary-dark: #a00a26; /* And this */
}
```

### Change Groq Model
Edit the `fetchCulturalInsights()` function:
```javascript
model: 'mixtral-8x7b-32768' // Try 'llama2-70b-4096' or others
```

## 📊 Technical Details

- **File size**: ~20KB (minified, no dependencies)
- **No build tools**: Zero npm packages
- **Offline support**: Lessons work without internet; cultural insights require API
- **Storage**: LocalStorage (5-10MB available in most browsers)
- **APIs used**: 
  - ElevenLabs (text-to-speech)
  - Groq (LLM for cultural insights)
  - Tailwind CSS CDN (styling)

## 🐛 Troubleshooting

### Audio not playing?
- Check ElevenLabs API key in config
- Verify browser allows audio autoplay
- Check browser console (F12) for errors

### Cultural insights not loading?
- Verify Groq API key is correct
- Check internet connection
- Try clicking the refresh button (🔄)
- Check rate limits on Groq dashboard

### Lessons not appearing?
- Clear browser cache (Ctrl+Shift+Delete / Cmd+Shift+Delete)
- Open browser DevTools (F12) and check Console for errors

### Progress not saving?
- Check browser allows localStorage
- Private/Incognito mode doesn't persist localStorage

## 📄 License

Free to use, modify, and deploy. No attribution required.

---

**Happy learning! 🇩🇰📚**

Questions? Open an issue or check the code comments in `index.html`.