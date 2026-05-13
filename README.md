# 🛡️ Guardian Watch — AI Smart Safety System

> AI-powered offline safety wearable that protects women, students & elderly — even without network.

---

## 🚀 Quick Setup (5 minutes)

### Step 1 — Install Node.js
Download from: https://nodejs.org (choose LTS version)

### Step 2 — Get Twilio (free trial — makes real calls & SMS)
1. Go to https://twilio.com → Sign up free
2. Get your **Account SID**, **Auth Token**, **Phone Number**
3. Verify your family members' phone numbers in Twilio console

### Step 3 — Clone & Setup
```bash
git clone https://github.com/YOUR_USERNAME/guardian-watch.git
cd guardian-watch/backend
npm install
cp .env.example .env
```

### Step 4 — Fill your .env file
```
TWILIO_ACCOUNT_SID=ACxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
TWILIO_AUTH_TOKEN=your_auth_token_here
TWILIO_PHONE_NUMBER=+1234567890

CONTACT_1=+919876543210   ← Amma's number
CONTACT_2=+919876543211   ← Appa's number
CONTACT_3=+919876543212   ← Harini's number
CONTACT_4=+919876543213   ← Rajan Uncle's number
CONTACT_5=+919876543214   ← Meena Akka's number

TEST_POLICE_NUMBER=+919876543210   ← use your number for testing
PORT=3000
```

### Step 5 — Run
```bash
node server.js
```

### Step 6 — Open app
Open browser → http://localhost:3000

---

## 🎯 What works in real life

| Feature | How it works |
|---|---|
| **SOS Button** | Calls all 5 family members simultaneously via Twilio |
| **SMS Location** | Sends Google Maps link to all contacts via Twilio SMS |
| **Call Police** | Say "call 100" or tap — auto-calls police (or test number) |
| **Voice Commands** | Say anything in Tamil or English — AI responds and acts |
| **Call any contact** | Say "call Amma" → she gets a real phone call |
| **Live location** | Real GPS shared via Socket.io to family dashboard |
| **Siren** | Real audio siren plays from device speakers |
| **Navigation** | Voice guides you step by step to nearest safe spot |
| **Follower detection** | Simulates + triggers auto-police call when too close |
| **Offline mode** | Demo shows all 4 backup layers activating |
| **Battery mode** | Shows emergency reserve behaviour |

---

## 📁 Project Structure

```
guardian-watch/
├── backend/
│   ├── server.js          ← Express + Socket.io + Twilio
│   ├── package.json
│   └── .env.example       ← Copy to .env and fill
└── frontend/
    └── public/
        └── index.html     ← Complete app (served by backend)
```

---

## 🗣️ Voice Commands (Tamil & English)

| Say this | What happens |
|---|---|
| "help" / "உதவி" | SOS activates — calls all family |
| "call police" / "போலீஸ்" / "100" | Real phone call to police |
| "call Amma" / "அம்மாவை அழை" | Real call to Amma |
| "I am safe" / "பத்திரம்" | SOS cancelled, family notified |
| "siren" / "சைரன்" | Loud siren activates |
| "police booth" | Navigation starts to police |
| "hospital" / "மருத்துவமனை" | Navigation starts to hospital |
| "safe shop" / "கடை" | Navigation to nearest safe shop |

---

## 🔧 Tech Stack

| Layer | Technology |
|---|---|
| Backend | Node.js + Express |
| Real-time | Socket.io |
| Calls & SMS | Twilio API |
| Voice AI | Web Speech API (browser) |
| Frontend | Vanilla HTML/CSS/JS |
| GPS | Browser Geolocation API |
| Audio | Web Audio API (siren) |

---

## 🌐 Deploy to cloud (free)

### Railway.app (easiest)
```bash
npm install -g railway
railway login
railway init
railway up
```

### Render.com
1. Push to GitHub
2. Go to render.com → New Web Service
3. Connect your GitHub repo
4. Root directory: `backend`
5. Build: `npm install`
6. Start: `node server.js`
7. Add all .env variables in Render dashboard

---

## ⚠️ Important Notes

1. **Twilio free trial** — you can only call verified numbers. Add family numbers to Twilio verified list.
2. **Police (100)** — Twilio cannot directly dial Indian emergency numbers. Use a middleman number for demo, or integrate with India's emergency API when available.
3. **Voice recognition** — works best in Chrome browser. Allow microphone permission.
4. **HTTPS required** — for voice recognition on deployed version, use HTTPS (Render/Railway gives this free).

---

## 👩‍💻 Built by

Guardian Watch — AI4India Hackathon Project
Smart Cities category — Women & Public Safety
