# Alkimi Agentic Platform Naming Poll

Interactive voting poll with real-time Google Sheets integration.

## 📁 Files Included

| File | Purpose |
|------|---------|
| `alkimi-poll.html` | Standalone HTML version - ready to deploy |
| `google-apps-script.js` | Backend code for Google Sheets |
| `agentic-platform-poll-sheets.jsx` | React component version (optional) |

---

## 🚀 Quick Setup (15 minutes)

### Step 1: Create the Google Sheet

1. Go to [Google Sheets](https://sheets.google.com) and create a new spreadsheet
2. Rename it to "Alkimi Platform Naming Poll"
3. Rename the first sheet tab to **"Votes"**
4. Add these headers in Row 1:

| A | B | C | D |
|---|---|---|---|
| Timestamp | Name | Voter | Email |

### Step 2: Deploy the Apps Script Backend

1. In your Google Sheet, go to **Extensions → Apps Script**
2. Delete any existing code in the editor
3. Copy and paste the entire contents of `google-apps-script.js`
4. Click **Save** (💾 icon)
5. Run the `setupSheet` function once:
   - Select `setupSheet` from the dropdown
   - Click **Run**
   - Authorize the script when prompted
6. Deploy as Web App:
   - Click **Deploy → New Deployment**
   - Click the gear icon ⚙️ → Select **Web app**
   - Set "Execute as" to **Me**
   - Set "Who has access" to **Anyone** (or "Anyone with Google Account" for more security)
   - Click **Deploy**
   - **Copy the Web App URL** - you'll need this!

### Step 3: Configure the Poll

1. Open `alkimi-poll.html` in a text editor
2. Find this line near the top:
   ```javascript
   const GOOGLE_SCRIPT_URL = 'YOUR_GOOGLE_APPS_SCRIPT_URL_HERE';
   ```
3. Replace `YOUR_GOOGLE_APPS_SCRIPT_URL_HERE` with your Web App URL from Step 2

### Step 4: Deploy the Poll

**Option A: GitHub Pages (Recommended)**
1. Create a new GitHub repository
2. Upload `alkimi-poll.html` (rename to `index.html`)
3. Go to Settings → Pages → Enable GitHub Pages
4. Share the URL with your team!

**Option B: Internal Server**
- Simply host the HTML file on any web server

**Option C: Local Testing**
- Open `alkimi-poll.html` directly in a browser (some features may require a server)

---

## 📊 Viewing Results

- **Real-time in poll**: Results show immediately after voting
- **Google Sheet**: All votes logged with timestamp, name choice, voter name, and email
- **Tally Sheet**: Auto-generated summary with vote counts and percentages

---

## 🔒 Features

- ✅ One vote per email (prevents duplicate voting)
- ✅ Anonymous option (name is optional)
- ✅ Real-time updates (polls every 30 seconds)
- ✅ Confetti celebration on vote submission
- ✅ Mobile responsive design
- ✅ Results sorted by vote count after voting

---

## 🎨 Customization

### Add/Remove Name Options
Edit the `namingOptions` array in the HTML file:

```javascript
const namingOptions = [
  { name: 'Anvil', emoji: '🔨', tagline: 'Forged for strength' },
  // Add or remove entries here
];
```

### Change Colors
The poll uses Tailwind CSS. Main gradient classes:
- Background: `from-slate-900 via-purple-900 to-slate-900`
- Accent: `from-purple-400 to-pink-400`

---

## 🛠 Troubleshooting

| Issue | Solution |
|-------|----------|
| "Failed to fetch votes" | Check that your Apps Script URL is correct and deployed |
| Votes not saving | Ensure Apps Script has permission to edit the Sheet |
| CORS errors | Make sure you're using `mode: 'no-cors'` in fetch requests |
| Already voted message | Clear localStorage: `localStorage.removeItem('alkimi_poll_email')` |

---

## 📧 Support

Questions? Reach out to Alice or the Automation team.

Happy voting! 🗳️
