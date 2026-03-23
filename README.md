# GlosArray
### Glosario Alfabéticamente Ordenado Automáticamente

GlosArray is a free, open source glossary web app that lets you store, view, add, edit, and delete vocabulary words — all connected to your own Google Sheet as a database. No servers, no accounts, no cost.

---

## ✨ Features

- 📖 **Ver** — View your full glossary in a clean table with live search
- ➕ **Agregar** — Add new words with dynamic numbered fields for definitions, synonyms, antonyms, examples, and sources
- ✏️ **Editar** — Edit any existing word with a pre-filled form
- 🗑️ **Eliminar** — Delete words with a confirmation modal to prevent accidents
- 🔤 **Auto-sort** — The glossary is automatically sorted alphabetically every time you add or edit a word
- 🔗 **Your data, your Sheet** — Each user connects their own Google Sheet via Apps Script

---

## 🛠️ Tech Stack

- HTML, CSS, JavaScript (Vanilla)
- [jQuery 3.3.1](https://jquery.com/)
- [Google Apps Script](https://script.google.com/) (backend)
- [Google Sheets](https://sheets.google.com/) (database)
- [Orbitron](https://fonts.google.com/specimen/Orbitron) — Google Fonts

---

## ⚙️ Setup Guide

GlosArray uses **Google Apps Script** as its backend. Each user needs to do this one-time setup to connect their own Google Sheet.

### Step 1 — Create a Google Sheet

1. Go to [sheets.google.com](https://sheets.google.com)
2. Create a new **blank spreadsheet**
3. Name it anything you like (e.g. `Mi Glosario`)
4. Leave it empty — GlosArray will create the header row automatically

---

### Step 2 — Add the Apps Script

1. In your Google Sheet, click **Extensions → Apps Script**
2. A new tab opens with a code editor
3. **Delete** all the default code in the editor
4. **Copy and paste** the entire contents of [`Code.gs`](./Code.gs) from this repo
5. Click 💾 **Save** (or `Ctrl+S`)
6. Name the project anything, e.g. `GlosArray`

---

### Step 3 — Deploy as a Web App

1. Click **Deploy → New deployment**
2. Click the ⚙️ gear icon next to "Select type" → choose **Web App**
3. Set the following:
   - **Description:** `GlosArray v1` (or anything)
   - **Execute as:** `Me`
   - **Who has access:** `Anyone`
4. Click **Deploy**
5. Google will ask you to **authorize** the app — click through and allow it
6. Copy the **Web App URL** — it looks like this:
   ```
   https://script.google.com/macros/s/AKfycb.../exec
   ```
   > ⚠️ Keep this URL private — it gives full access to your Sheet. Do not share it publicly or commit it to GitHub.

---

### Step 4 — Connect to GlosArray

1. Open `index.html` in your browser
2. Paste your Web App URL into the text field
3. Click **Guardar URL**
4. You should see ✅ — you're ready to use all features!

---

### ⚠️ Important — Redeploying after script changes

If you ever modify `Code.gs`, you must redeploy for changes to take effect:

1. Click **Deploy → Manage deployments**
2. Click the ✏️ edit icon on your existing deployment
3. Change the version to **"New version"**
4. Click **Deploy**

---

## 📁 File Structure

```
GlosArray/
├── index.html       # Home page — save your Web App URL here
├── ver.html         # View all words
├── agregar.html     # Add a new word
├── editar1.html     # Edit an existing word
├── eliminar.html    # Delete a word
├── header.html      # Shared navigation header
├── footer.html      # Shared footer
└── Code.gs          # Google Apps Script backend
```

---

## 🔒 Privacy & Security

- Your Web App URL is stored only in your **browser's localStorage** — it is never in the source code
- Each user connects their **own private Google Sheet** — no shared database
- The Apps Script runs under **your own Google account**

---

## 📄 License

This project is licensed under the [MIT License](./LICENSE).

---

## 👤 Author

**Islas Ramírez, Ian Carlo**
