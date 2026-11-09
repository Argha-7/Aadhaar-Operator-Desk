# Aadhaar Operator Desk Assistant - Operator Manual

## 📱 Quick Overview
This application is designed specifically for Aadhaar Enrolment & Update Centre operators to:
1. **Track daily customer counts** across 3 age categories (`Under 5`, `5 to 18`, `18 and Above`).
2. **Instant 1-Tap Logging** with audio click & mobile vibration feedback.
3. **Know exact mandatory form fields** for each service based on official UIDAI forms:
   - **Form 1:** 18+ Years (Adults)
   - **Form 3:** 5 to 18 Years (Minors & MBU)
   - **Form 5:** Below 5 Years (Bal Aadhaar)
4. **Reorder Buttons** & **Customize Mandatory Fields** anytime without writing code.
5. **Smart Undo** to correct accidental double-taps.
6. **Set / Calibrate Counter** manually if starting mid-day.
7. **Seat Operator Name Tracking** to record who is operating the counter.
8. **1-Click Excel (CSV) Export** for end-of-day tally & record-keeping.

---

## 🚀 How to Run on PC & Mobile (100% Offline)

### On Your PC / Laptop:
1. Double-click `Aadhaar_Kendra_Assistant.html` in this folder.
2. It will open in Google Chrome or Microsoft Edge.
3. No internet connection is needed—it works completely offline!

### On Your Mobile Phone (Android / iPhone):
1. Send `Aadhaar_Kendra_Assistant.html` to your phone via WhatsApp, Gmail, or USB cable.
2. Open it in Chrome on your phone.
3. Tap the **3 dots (⋮)** in the top right corner of Chrome.
4. Select **"Add to Home screen"** (or "Install app").
5. The assistant will now open like a native mobile app in full screen!

---

## ⌨️ PC Keyboard Shortcuts (For Fast Desktop Entry)
If you are operating on a desktop PC with a physical keyboard:
* **Keys `1` to `9` & `0`:** Instantly log count for Services 1 to 10 (including newly added Advance Cards in your custom button order)!
* **Key `U`:** Instantly Undo the last recorded tap.
* **Key `Q`:** Switch to **Under 5 Years (Form 5)**.
* **Key `W`:** Switch to **5 to 18 Years (Form 3)**.
* **Key `E`:** Switch to **18 and Above (Form 1)**.

---

## ⚙️ How to Customize Your Assistant

### 1. Editing Mandatory Form Fields (From Inside the Screen):
* Tap on the **`(i)` button** of any service (e.g. *Bio Update*, *Mobile*, *Name*).
* On that screen, tap the **`✏️ Edit`** button (available in the modal header and at the bottom).
* It directly opens the field editor for that service where you can add/edit boxes or restore to UIDAI defaults!

### 2. 🎬 Movie-Style 18 Counter Seats (4 Seats Per Row):
* Directly below the **Advance Options** dropdown, you have **18 Movie-Style Counter Seats** (`01` to `18`) arranged **4 seats per row** (Rows 1-4: 4 seats each, Row 5: 2 centered seats).
* **Default State:** All 18 seats default to **🟢 Green (Active)**.
* **Double-Click to Close (🔴 Closed):** Simply **double-click any seat** to instantly toggle it between **🔴 Closed** and **🟢 Active**!
* **Hover for Full Name:** Hover your mouse over any seat to reveal a tooltip with the operator's complete name and desk status.
* **Assign Operator Name:** Click once on any seat to select it (glowing blue border), type the operator's name in the field below, and press **Enter** or tap **Save**.
* **Live Desk Counter:** Shows real-time count of active vs closed desks (e.g. `18 Active | 0 Closed`).
* **Excel Export Integration:** The daily Excel export automatically includes the full operator seating roster along with service totals!

### 3. 📋 Bulk Paste WhatsApp Operator Roster:
* In the **⚙️ Advance Options & Tools** dropdown, click **`📋 Bulk Paste Operator Roster`**.
* Paste your daily WhatsApp group seating duty list (e.g. `1. Rahul Sharma`, `2. Pooja Verma`, `3. Amit Kumar` or plain names line-by-line).
* Click **"⚡ Apply to 18 Counter Seats"**—it automatically fills seats 01 to 18 in 1-click!
* **Daily Auto-Refresh:** Roster is locked for today only. The next morning, seats automatically refresh fresh for the new day's WhatsApp roster!

### 4. 🔒 Silent Internal Firebase Cloud Sync:
* **Zero UI Clutter:** Firebase connects **internally in the background** without any distracting buttons, badges, or configuration popups on screen.
* **Pre-Configured Credentials:** The official project `aadhaar-operator-desk` is pre-configured directly into the code.
* **Real-Time Cloud Mirroring:** Every logged transaction, daily total, and seating snapshot automatically syncs to Google Firestore in the background.
* **100% Offline First:** If internet connectivity drops, the assistant runs flawlessly on the local indexed database without any error prompts.
* **Firestore Security Rules Tip:** In your [Firebase Console](https://console.firebase.google.com) ➔ **Firestore Database** ➔ **Rules** tab, ensure your rules allow read and write (e.g. Test Mode `allow read, write: if true;`) so unauthenticated desk clients can sync tallies seamlessly.

### 5. 🚀 How to Deploy on Vercel (Free 1-Click Cloud Hosting):
* You **do not strictly need Vercel** to use the app—you can run it offline on any PC or phone simply by opening `index.html` or `Aadhaar_Kendra_Assistant.html`.
* **However, if you want a public web link** (e.g. `https://your-center.vercel.app`) so all 18 operators can open the app on their phones or terminals without copying files:
  1. Go to [vercel.com](https://vercel.com) and sign in.
  2. Click **"Add New Project"** ➜ Select **"Upload"** or connect your GitHub repository with this `AAdherIN` folder.
  3. The `vercel.json` and `index.html` files are already configured for you.
  4. Click **"Deploy"**—within 10 seconds, your custom Kendra live URL will be active!

### 6. 🔄 Changing Button Order & Counter Calibration:
* Click **`🔄 Change Button Order`** to arrange services using ▲ and ▼ arrows.
* Click **`🔢 Counter Calibration / Set`** to set or adjust the starting token count.
* Click **`🗑️ Reset Current Day Counts`** (inside Advance Tools) whenever you want to reset counts manually.

---

## 📋 UIDAI Form Box Mapping (Quick Reference)

| Service | Official Form Boxes to Fill | Required Proof |
| :--- | :--- | :--- |
| **`bio update`** | Field 1 (Update), Field 2 (Resident Indian), Field 7(a) (Aadhaar No), Field 7(b) (Biometric), Signature | No docs for MBU (Age 5 & 15). Existing Aadhaar for adult. |
| **`mobile`** | Field 1, Field 2, Field 3(e) (Mobile No), Field 7(a), Field 7(b) (Mobile), Signature | **No documents required.** Real-time OTP verification. |
| **`Name`** | Field 1, Field 2, Field 3(a) (New Name in CAPITAL), Field 4 (Doc verify), Field 5(b)(i) (POI Doc Name), Field 7(a), Field 7(b) (Name), Signature | Original POI (PAN, Voter ID, Passport, DL). Max 2 times in life. |
| **`date of birth`** | Field 1, Field 2, Field 3(c) (DDMMYYYY + Verified), Field 4, Field 5(b)(iii) (POB Doc Name), Field 7(a), Field 7(b) (DOB), Signature | Municipal Birth Certificate / 10th Board Marksheet. Max 1 time. |
| **`Gender`** | Field 1, Field 2, Field 3(b) (Gender tick), Field 7(a), Field 7(b) (Gender), Signature | Medical certificate / Self declaration. Max 1 time. |
| **`Address`** | Field 1, Field 2, Field 4, Field 5(a) (Address + Post Office + PIN code), Field 5(b)(ii) (POA Doc Name), Field 7(a), Field 7(b) (Address), Signature | Original POA (Electricity bill < 3 months, Bank passbook, etc.) or HoF Mode. |
| **`Email`** | Field 1, Field 2, Field 3(d) (Email ID), Field 7(a), Field 7(b) (Email), Signature | **No documents required.** Real-time email OTP. |
| **`Update of POI/POA`** | Field 1, Field 2, Field 4, Field 5(b)(i) (POI Doc), Field 5(b)(ii) (POA Doc), Field 7(a), Field 7(b), Signature | 1 Original POI + 1 Original POA. Mandatory for 10-year-old Aadhaars. |

---

## 📜 Database & Operational History (Daily Audit Trail)
* Click the **`📜 History`** button located at the bottom app bar.
* **Date Dropdown:** Select any recorded date (e.g. `10 Nov 2026 (Today)`, `09 Nov 2026`, etc.).
* **Tab 1 - Day Breakdown:** View exact day total, 3-age category breakdown (`Under 5`, `5-18`, `18+`), 8 service counts, and active operator desks on that day.
* **Tab 2 - Live Audit Log:** Shows the exact timestamp (`10:45:12 AM`), service, age group, counter seat, and operator.
* **Automatic Day Rollover:** Opening the app on a new day archives yesterday's numbers in the history database automatically without losing any data!
* **Master History Export:** Download the entire historical database across all days to Excel (CSV) with one click.

---

## 🔒 End-of-Day Routine for Operator
1. **Download Excel:** Click **`📥 Excel`** at the bottom right to download the CSV summary of the day's total work for your audit.
2. **Review History:** Click **`📜 History`** to verify total tokens issued by each counter and operator.
3. **Daily Reset (Automatic):** The assistant automatically archives yesterday's tallies and refreshes seats fresh the next morning. Manual reset is also available under Advance Options.
