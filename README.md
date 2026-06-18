# 🐼 Panda HSK — Chinese Vocabulary Trainer

A friendly, single-file web app for learning **HSK 1–3** Chinese vocabulary (1000 words) with
flashcards and quizzes. Meet **Bao**, your panda study buddy, who reacts as you learn.

![level](https://img.shields.io/badge/HSK-1--3-4c9a4f) ![words](https://img.shields.io/badge/words-1000-2f6b33) ![license](https://img.shields.io/badge/license-MIT-e7a83b)

## ✨ Features

- **Study mode** — flip-card flashcards. Choose to see 汉字, 拼音, or English first.
- **Quiz mode** — multiple-choice questions (character ⇄ meaning), score tracking, and a
  best-score record that's saved on your device.
- **Browse mode** — search the full list by character, pinyin (with or without tone marks), or English.
- **HSK level tabs** — switch between **HSK 1 / HSK 2 / HSK 3 / All** on every page.
- **Pronunciation** — tap the speaker to hear each word read aloud (uses your browser's
  built-in Chinese voice, where available).
- **Works offline** once loaded, and on phones, tablets, and desktops.

Everything lives in one file (`index.html`) — no build step, no server, no dependencies.

---

## 📁 What's in this repo

| File | What it is |
|------|------------|
| `index.html` | The complete app (vocabulary is built in). **This is the only file you need to publish.** |
| `vocab-data.js` | The vocabulary as clean, editable data — handy if you want to add HSK 4+ later (see below). |
| `README.md` | This file. |
| `USER-GUIDE.md` / `USER-GUIDE.pdf` | A guide for learners. |

---

## 🚀 Publish it on GitHub Pages (step by step)

You don't need to know any coding. This takes about 5 minutes.

### 1. Create a new repository
1. Sign in to [github.com](https://github.com) (create a free account if you don't have one).
2. Click the **+** in the top-right corner → **New repository**.
3. Give it a name, e.g. `panda-hsk`.
4. Set it to **Public**.
5. Leave everything else as-is and click **Create repository**.

### 2. Upload the files
1. On your new empty repository page, click **uploading an existing file**
   (the link in the "Quick setup" box). Or go to **Add file → Upload files**.
2. Drag in **`index.html`** (and optionally the other files).
3. Scroll down and click **Commit changes**.

### 3. Turn on GitHub Pages
1. In your repository, click **Settings** (top menu).
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, pick **`main`** and folder **`/ (root)`**, then click **Save**.

### 4. Visit your live app
- Wait about 1–2 minutes. Refresh the **Pages** settings screen.
- A green box appears: *"Your site is live at …"*
- Your address will look like:
  ```
  https://YOUR-USERNAME.github.io/panda-hsk/
  ```
- Open it, bookmark it, and share it. 🎉

> **Tip:** Whenever you change a file, just upload the new version (**Add file → Upload files**,
> commit). GitHub Pages updates the live site within a minute or two.

---

## 🧩 Adding HSK 4 (or editing words)

The app reads its words from a single object called `HSK_DATA` near the bottom of `index.html`,
inside the `<script>` block. Each word looks like this:

```js
{"h":"爱","p":"ài","pos":"verb","e":"to love"}
```
- `h` = hanzi (the character)
- `p` = pinyin
- `pos` = part of speech
- `e` = English meaning

To **add a new level**, add a `"4":[ ... ]` array to `HSK_DATA`, then add a matching tab button
in the level bar:

```html
<button data-lv="4" aria-pressed="false">HSK 4<small>… words</small></button>
```

The clean, comment-headed copy in **`vocab-data.js`** is the easiest place to prepare new data —
copy your finished `HSK_DATA` object from there into `index.html`.

> Prefer to keep data in a separate file? Replace the inline `HSK_DATA` block in `index.html`
> with `<script src="vocab-data.js"></script>` placed **before** the main script. This works on
> GitHub Pages and when opening the file locally.

---

## 💻 Run it locally

Just **double-click `index.html`** — it opens in your browser. No installation needed.

---

## 📚 Credits & license

- Vocabulary: the official **New HSK** word lists (Levels 1–3), as compiled by MandarinBean.
- Released under the **MIT License** — free to use, modify, and share.
