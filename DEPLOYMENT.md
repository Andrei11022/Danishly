## 📋 Deployment Checklist

Follow these steps to deploy Danishly to GitHub Pages:

### Step 1: Get Your API Keys

#### ElevenLabs (for audio pronunciation)
1. Go to https://elevenlabs.io
2. Sign up for free (includes 10,000 free characters/month)
3. Navigate to Settings → API Keys
4. Copy your API Key
5. (Optional) View available voice IDs at https://elevenlabs.io/docs/api/text-to-speech to customize the voice

#### Groq (for cultural insights)
1. Go to https://console.groq.com
2. Sign up for free (very generous free tier)
3. Click "API Keys" in the left menu
4. Create a new API key
5. Copy it

### Step 2: Configure the App
1. Open `index.html` in a text editor (VS Code, Notepad, etc.)
2. Find the line: `ELEVENLABS_API_KEY: 'your_elevenlabs_api_key_here'`
   - Replace with your actual ElevenLabs API key
3. Find the line: `GROQ_API_KEY: 'your_groq_api_key_here'`
   - Replace with your actual Groq API key
4. (Optional) Change the voice by finding the `ELEVENLABS_VOICE_ID` line
   - See voice options at https://elevenlabs.io/docs/api/text-to-speech
5. Save the file

### Step 3: Test Locally (Recommended)
1. Double-click `index.html` to open it in your browser
2. You should see the warning banner asking for API keys - it will disappear after you add them
3. Try these features:
   - Click **🔊 Listen** on any word to test ElevenLabs
   - Click **🔄** next to "Danish Culture" to test Groq
   - Try the **Flashcards** tab to test offline functionality
4. If you see errors in the browser console (F12), check that:
   - Your API keys are correct (no extra spaces)
   - You've enabled CORS if needed (ElevenLabs/Groq should handle this)

### Step 4: Deploy to GitHub Pages

#### Option A: Using GitHub Web UI (Easiest - No Terminal Needed)
1. Go to https://github.com/new
2. Create a new repository:
   - **Repository name:** `Danishly`
   - **Description:** (optional) "A Danish language learning app"
   - **Public** ✅ (required for free GitHub Pages)
3. Click "Create repository"
4. **Upload your files:**
   - Drag and drop `index.html` onto the page, OR
   - Click "uploading an existing file" and select `index.html`
   - (Optional) Also upload `README.md` and this file
5. Click "Commit changes"
6. Go to **Settings → Pages**
   - Select `main` branch as the source
   - Click "Save"
7. Wait a moment, then visit: `https://your-username.github.io/Danishly`
   - Your app is live! 🎉

#### Option B: Using Git/Terminal (For experienced users)
```powershell
# Navigate to your project folder
cd C:\Users\DLA\Danishly

# Initialize git if not already done
git init

# Add all files
git add .
git commit -m "Initial commit: Add Danishly Danish learning app"

# Rename to main branch if needed
git branch -M main

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/Danishly.git

# Push to GitHub
git push -u origin main
```

Then enable Pages in Settings → Pages (select `main` branch).

### Step 5: Share & Enjoy! 🇩🇰

Your app is now live at: **`https://your-username.github.io/Danishly`**

**Tips:**
- The app works offline once loaded (all lessons are cached in your browser)
- Cultural insights are cached for 1 hour to save API calls
- All progress is saved in your browser's local storage
- Share the URL with friends to help them learn Danish!

---

## 🔒 Security Notes

- **API Keys in HTML:** Since this is a frontend-only app deployed to GitHub Pages, your API keys will be visible in the HTML source. This is intentional for simplicity.
- **Rate Limits:** Both ElevenLabs and Groq have generous free tiers. Monitor your usage:
  - ElevenLabs: 10,000 characters/month free
  - Groq: ~30 requests/minute (very high)
- **Privacy:** All user progress is stored locally in their browser—nothing is sent to your server.

---

## 📱 Browser Compatibility

- ✅ Chrome/Edge (Recommended)
- ✅ Firefox
- ✅ Safari
- ⚠️ Internet Explorer (Not supported)

### Step 5: Enable GitHub Pages
1. [ ] Go to your repo on GitHub
2. [ ] Click **Settings** (top right)
3. [ ] Left sidebar: Click **Pages**
4. [ ] Under "Build and deployment":
   - Source: Select `Deploy from a branch`
   - Branch: Select `main`, folder: `/ (root)`
5. [ ] Click **Save**
6. [ ] Wait 1-2 minutes for deployment
7. [ ] Your site will be live at: `https://YOUR_USERNAME.github.io/Danishly/`

### Step 6: Share & Enjoy!
- [ ] Test the deployed link in your browser
- [ ] Share the link with friends!
- [ ] Make sure to keep your API keys private (they're only used client-side)

---

## ⚠️ Important Notes

### Keep API Keys Secret
- The API keys are stored in your `index.html` and sent directly from the user's browser to the APIs
- **Don't commit keys to GitHub** if you make your repo private or plan to open-source it
- If you want to keep this public, consider using a backend service or environment variables

### Rate Limits
- **ElevenLabs**: Free tier has limited characters/month. Check your dashboard.
- **Groq**: Free tier is very generous (~30 requests/minute)

### Custom Domain (Optional)
To use your own domain instead of `github.io`:
1. Add a CNAME file to the repo with your domain
2. Point your domain's DNS to GitHub Pages (see GitHub docs)

---

**Done! Your Danishly app is now live! 🎉**