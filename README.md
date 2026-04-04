# 📞 AutoDial Pro — User Guide

**The cold-calling power tool for Singapore financial consultants.**

---

## 🚀 Getting Started

### For Owners (Team Leaders)

1. Open AutoDial at your GitHub Pages URL
2. Log in with your email via Supabase
3. You're automatically assigned the **Main** role as the Owner
4. Go to **Settings** → connect Google → link your lead sheet

### For Admins (Managers)

1. Log in → select **Admin** role
2. Wait for Owner approval (one-time)
3. Once approved, your leads sheet will be linked by the Owner
4. Go to **Leads** tab → **Fetch Leads** to load your contacts

### For Mains (Callers)

1. Log in → select **Main** role
2. Wait for Owner approval (one-time)
3. Your admin will assign you a leads sheet
4. Go to **Leads** tab → **Fetch Leads** → start dialing!

---

## 📱 The Calling Flow

### Starting a Session

1. Tap **▶️ Start Session** (bottom of Dial tab)
2. If your admin set up multiple time slots, pick one (e.g., "5h challenge")
3. The first eligible lead loads automatically

### During a Call

You'll see the lead's name, phone, age, gender, email, and any remarks from the sheet.

**After each call, tap one of:**

| Button | What it does |
|--------|-------------|
| **NP** | No Pick — lead didn't answer. Auto-counts (NP x1, x2, x3…). After 5 NPs, auto-converts to NI |
| **CB** | Callback — pick a date/time. Lead enters the CB queue and surfaces when due |
| **NI** | Not Interested — lead is removed from the dial queue permanently |
| **Set** | Appointment Set! Creates a calendar event + appointment card |
| **Skip** | Don't mark anything — move to next lead |

### ⚡ Smart Auto-Dial

When you tap **NI** or **NP**, the app **instantly skips** to the next lead and starts dialing — no extra taps needed. You'll see a gold **↩️ Undo** bar for 10 seconds in case you made a mistake.

For **CB** and **Set**, a remarks screen appears so you can add notes before moving on.

### Post-Call Remarks

After CB/Set, you'll see:
- **"➡️ Next Lead"** — skip to next (no note)
- **"💾 Save & Next Lead →"** — saves your typed note and advances

---

## ⭐ Ranking System (Mains Only)

### How Ranks Work

Your rank is based on **appointments set this month**. Ranks reset on the 1st of every month.

| Rank | Emoji | Default Min Appts |
|------|-------|-------------------|
| Warrior | ⚔️ | 0 |
| Elite | 🛡️ | 5 |
| Master | 🏅 | 10 |
| Grandmaster | 💎 | 20 |
| Epic | 🌟 | 30 |
| Legend | 👑 | 40 |
| Mythic | 🏆 | 55 |

*(Owner can customize thresholds in Settings)*

### ⭐ Stars Economy

Stars are your **lifetime achievement currency**:

- **Milestone Stars** — earned when you rank up. Each rank awards bonus stars (e.g., Elite = +10⭐, Master = +25⭐). Each rank can only award once per month.
- **Stars per Dial** — earn a small amount for every call made (default 0.1⭐/dial)
- **Stars Bank** — on the 1st of each month, your current stars get **banked** into your lifetime total. Your monthly stars reset, but your bank keeps growing forever.

Your total Star Bank is displayed in Settings: "🏦 Star Bank: X ⭐"

### Monthly Reset

On the 1st of each month:
1. Current stars → added to Star Bank
2. Monthly rank → resets to Warrior
3. Milestone tracking → resets (earn them again!)
4. Toast: "🏦 X stars banked! New month, new grind."

---

## 🏆 Live Leaderboard

See how you stack up against other Mains in real-time!

- Go to the **Rank** tab → scroll down to **🏆 Today's Leaderboard**
- Shows all active callers ranked by appointments set today
- 🥇🥈🥉 Gold/Silver/Bronze for top 3
- Green dot = currently calling live
- Updates every 30 seconds automatically

---

## 📅 Appointments

### Call Mode
Shows only YOUR appointments (ones you set).

### Manage Mode (toggle CALL/MGMT)
Shows ALL appointments grouped by admin:
- **📞 My Appointments** — yours (shown first)
- **👤 Admin Name** — each admin's appointments with count

### Appointment Actions

| Button | What it does |
|--------|-------------|
| **Met ✅** | Meeting completed → adds incentive to current billing cycle |
| **Postponed** | Reschedule — stays in pending |
| **Fly Kite 🪁** | No-show |
| **Closed 💰** | Deal closed! Enter EFYC (Main) or Tip (Admin) amount |

### Important Notes
- Admin appointments do NOT count toward your Mythic rank
- Appointment status changes write back to the Google Sheet "Appointments Set" tab
- Deleting an appointment is permanent and syncs across all devices

---

## 🧠 AI-Powered Lead Analysis

### Claude AI (Recommended)

Claude analyzes your Google Sheet with 6 layers of intelligence:

1. **Column Detection** — identifies phone, name, DOB, remarks columns from headers + data
2. **Remark Classification** — understands "refund case pending" = NI, "husband will call back" = CB
3. **Name Extraction** — fixes leads where phone number shows as name
4. **Confidence Scoring** — flags uncertain column mappings so you can correct them
5. **Smart Dedup** — finds duplicate leads across batches
6. **Learning Loop** — when you correct a status, Claude learns related patterns

**Setup:**
1. Get an API key at [console.anthropic.com/settings/keys](https://console.anthropic.com/settings/keys) ($5 minimum credit)
2. Open AutoDial → **Settings** → **🧠 Claude AI** section
3. Paste your `sk-ant-...` key
4. Each user uses their own key — costs ~$0.04 per fetch (~$4/month)

### Gemini AI (Free Fallback)

If no Claude key is set, AutoDial uses Google Gemini for analysis. Add your Gemini key in Settings → 🤖 Gemini AI.

### 🔧 Manual Column Override

If AI gets columns wrong:
1. Go to **Leads** tab
2. Tap **🔧 Columns** button (next to search bar)
3. Reassign each column: Phone, First Name, DOB, Remarks, etc.
4. Tap **✅ Apply & Re-import**

---

## 🔌 Offline Mode

AutoDial works without internet!

- Leads are cached in your browser — you can keep calling even if WiFi drops
- Status changes (NI/NP/CB/Set) queue locally
- When connection returns: "📶 Back online — syncing…" and all changes push to Google Sheets
- Look for the **OFFLINE** badge in the header

---

## ↩️ Undo

Accidentally marked someone NI? No problem.

- After NI or NP, a gold **↩️ Undo** bar appears for **10 seconds**
- Tap it to reverse the status and jump back to that lead
- After 10 seconds, the undo option disappears

---

## 🛡️ Conflict Resolution

When two callers share the same lead sheet:

- Each lead is "claimed" when you start dialing them
- If another caller tries to dial the same lead within 10 minutes, they see:
  **"⚠️ John is already calling Stella Koh"**
- The app auto-skips to the next unclaimed lead
- Prevents wasted calls and awkward double-dials

---

## 🔄 Cross-Device Sync

AutoDial syncs across all your devices via Supabase:

- **Leads, settings, appointments, sessions** — all synced
- Start a session on desktop, continue on phone
- End a session on one device → other device detects it automatically
- If the app crashes, it **recovers your exact position** on reload (same lead, same session)

---

## 🔗 Google Integration

### Permanent Connection (via Cloudflare Worker)

Connect Google once → never again. Your refresh token is stored securely on Cloudflare.

- First time: tap "Connect Google" → popup → grant access → done forever
- Token auto-refreshes silently in the background
- Works across devices and sessions

### What's Connected

| Service | What AutoDial does |
|---------|-------------------|
| **Google Sheets** | Reads leads, writes back statuses, logs timesheets |
| **Google Calendar** | Creates appointment events with invites |
| **Google Drive** | Searches for your spreadsheets |

---

## ⚙️ Settings Reference

### Owner-Only Settings

| Setting | Description |
|---------|------------|
| Star Rank Thresholds | Min appointments per rank (Warrior=0, Elite=5…) |
| Milestone Stars | Stars awarded per rank-up (Elite=10⭐, Master=25⭐…) |
| Stars per Dial | Small star reward per call made |
| NP → NI Threshold | Auto-convert to NI after X no-picks (default: 5) |
| Queue Priority | Order of lead selection (Blank → CB Due → NP Retry) |

### All Users

| Setting | Description |
|---------|------------|
| Google Sheets | Link your lead spreadsheet |
| Gemini AI Key | For AI-powered lead analysis (free) |
| Claude AI Key | For smarter analysis ($0.04/fetch) |
| Call Delay | Seconds between auto-dial (adjustable during calls) |
| DNC Hours | Do Not Call window (e.g., 9pm–9am) |

---

## 📊 Status Abbreviations

AutoDial auto-detects these from your sheet remarks:

| Remark | Status | Meaning |
|--------|--------|---------|
| NI, N.I., not interested | NI | Not Interested |
| NP, NPx2, no pick, no answer | NP | No Pick |
| CB, callback, call back, call tmr | CB | Callback |
| appt set, appointment, date+time+location | Set | Appointment Set |
| WN, wrong number | NI | Wrong Number → treated as NI |
| DNC, do not call, DND | NI | Do Not Call → treated as NI |
| deceased, passed away | NI | Treated as NI |
| refund, cancelled | NI | Treated as NI |

**Custom patterns:** When you see "⚠ UNRECOGNIZED" and pick a status, AutoDial remembers that pattern forever. Claude AI also learns related variations automatically.

---

## 💡 Tips & Tricks

- **Speed dial**: Reduce delay to 1-3 seconds in Settings for maximum throughput
- **Quick NI**: One tap and you're already calling the next person
- **Undo safety net**: Don't worry about mis-taps — you have 10 seconds to fix it
- **Star grinding**: Even NP calls earn stars per dial. Every call counts!
- **Column override**: If AI gets your sheet wrong, the 🔧 button fixes it instantly
- **Leaderboard motivation**: Check the Rank tab to see who's crushing it today

---

## 🆘 Troubleshooting

| Issue | Fix |
|-------|-----|
| App crashes on load | Clear browser cache, reload. Your data is safe in Supabase |
| Google popup keeps appearing | This shouldn't happen with the Worker. Check Settings → Google |
| Leads not loading | Check Google connection, verify sheet URL in Settings |
| NI leads still showing | Hard refresh (Ctrl+Shift+R). If persists, re-fetch leads |
| Session won't start | Check if a stale session exists — it auto-clears after 24h |
| Dial loops back to same lead | Update to latest version — this was fixed with pre-computed navigation |
| "OFFLINE" showing | Check your internet connection. Changes will sync when back online |

---

*AutoDial Pro — Built for speed. Designed for results.* 🚀
