# For You My Love 💕

A sweet, password-protected love website you can personalize and share with someone special. Everything lives in a single `index.html` file — no install or build step required.

## Quick start

1. Open `index.html` in any text editor (VS Code, Notepad++, etc.).
2. Customize the `CONFIG` section and content (see below).
3. Double-click `index.html` to preview in your browser, or host it for free on [GitHub Pages](https://pages.github.com/), [Netlify](https://www.netlify.com/), or [Vercel](https://vercel.com/).

---

## How to change the password

Near the bottom of `index.html`, find the **CONFIG** block inside the `<script>` tag:

```javascript
const CONFIG = {
    password: 'iloveyou',           // Secret code to unlock the site (not case-sensitive)
    welcomeMessage: 'Welcome my love, enjoy your stay',
    passwordTitle: 'Enter the secret code',
    passwordPlaceholder: 'Our special word...',
    wrongPasswordPlaceholder: 'Try again, my love...'
};
```

Change `password` to your own secret word or phrase:

```javascript
password: 'ouranniversary2024',
```

The check is **not case-sensitive** — `ILoveYou` and `iloveyou` both work.

> **Note:** This is a front-end-only lock. Anyone who views the page source can find the password. It is meant as a cute surprise, not real security.

---

## CONFIG options

| Setting | What it does |
|--------|----------------|
| `password` | Secret code required to enter the site |
| `welcomeMessage` | Text shown on the welcome screen after unlocking |
| `passwordTitle` | Heading on the password popup |
| `passwordPlaceholder` | Hint text inside the password input |
| `wrongPasswordPlaceholder` | Message shown when the wrong password is entered |

---

## Customize the content

### Page title (browser tab)

In the `<head>` section, change:

```html
<title>For My Love</title>
```

### Love letter

Find the **Love Letter** tab (`id="love-letter"`). Edit the letter text inside `.letter-content`, and change the greeting in `<h2>My Dearest</h2>`.

Click the letter on the page to expand or collapse it.

### Music

In the **Music** tab (`id="music"`), each `.song` block is one entry:

```html
<div class="song">
    <div class="song-icon">🎵</div>
    <div class="song-info">
        <h4>Your Song Title</h4>
        <p>by Artist Name</p>
    </div>
</div>
```

Copy a `.song` block to add more songs.

### Notes

In the **Notes** tab (`id="notes"`), edit or add `.note` blocks:

```html
<div class="note">
    <p>Your reminder here</p>
</div>
```

### Gallery

In the **Gallery** tab (`id="gallery"`), replace image URLs in each `.gallery-item`:

```html
<div class="gallery-item">
    <img src="path-or-url-to-your-photo.jpg" alt="Description of the image">
</div>
```

You can use:
- **Online URLs** — upload to Imgur, Google Drive (public link), or similar
- **Local files** — put images in an `images/` folder next to `index.html` and use `src="images/photo1.jpg"`

---

## Customize colors & style

All styles are in the `<style>` block at the top of `index.html`. Common tweaks:

| Element | CSS property | Default |
|--------|--------------|---------|
| Page background | `body` → `background` | Pink gradient `#ffd1dc` → `#ffb7c5` |
| Main accent color | `#d81b60` (used in headings, buttons, tabs) | Deep pink |
| Button hover | `.submit-btn:hover` → `background` | `#b71550` |
| Fonts | Google Fonts link in `<head>` | Dancing Script + Montserrat |

Example — switch to a purple theme:

```css
body {
    background: linear-gradient(135deg, #e8d5f5, #d4b8e8);
}
```

Then find-and-replace `#d81b60` with your accent color (e.g. `#7b1fa2`).

---

## Tab labels

Each tab button uses a `data-tab` attribute that must match its content `id`:

```html
<button class="tab active" data-tab="love-letter">
    <span>❤️</span> Love Letter
</button>
```

Change the label text and emoji freely; keep `data-tab` and the matching `id` in sync.

---

## Share the site

**Local:** Send the `index.html` file (and any local images) to your partner.

**Online (free):**
1. Push the project to a GitHub repository.
2. Go to **Settings → Pages** and deploy from the `main` branch.
3. Share the link (e.g. `https://yourusername.github.io/foryoumylove/`).

Tell them the secret password separately for the surprise. 💌
