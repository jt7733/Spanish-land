# Mi Español — El Reino de Solaria

One folder, three ways to run it: Android app, Windows app, or plain browser.

---

## Android (recommended — mic and Spanish voices both work here)

This folder is a PWA. Put it on the web once, then install it from Chrome like any app.

### 1. Host it (free, ~5 minutes, once)

**GitHub Pages**
1. Create a free account at github.com, then a new repository called `mi-espanol` (public).
2. Upload every file in this folder (drag them onto the repo page → Commit).
3. Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: main → Save.
4. After a minute your app is live at `https://YOURNAME.github.io/mi-espanol/`

**Netlify Drop** (alternative): app.netlify.com/drop → drag this folder in → you get a URL.

### 2. Install it on your phone

Open that URL in **Chrome** on Android → tap the ⋮ menu → **Install app** (or "Add to Home screen").
It gets its own icon, opens full-screen with no browser bar, and works offline.

The story, boss fights and writing review need your Anthropic API key
(console.anthropic.com → API keys). A panel asks for it the first time. Everything else works without one.

### Voices on Android
Google's speech engine usually ships Spanish already. In the app: **Yo → Ajustes de voz** — you should see
several "es-MX / es-US" voices. Tap to audition; pick the one you like.
If none appear: Settings → System → Languages → Text-to-speech → Google → Install voice data → Español (México).

### Real APK instead? (optional, heavier)
If you want it in the Play Store or as an installable .apk, wrap this folder with Capacitor:

    npm install @capacitor/core @capacitor/cli @capacitor/android
    npx cap init "Mi Espanol" com.justin.miespanol --web-dir .
    npx cap add android
    npx cap open android      ← opens Android Studio; Build → Build APK

Requires Android Studio (~1 GB). The PWA route above gives you 95% of that for none of the setup.

---

## Windows

**No install:** double-click `index.html`.
**Own window:** shortcut to `msedge.exe --app="C:\path\to\index.html"`.
**Real .exe:** install Node.js, then `npm install`, `npm start`. `npm run build` makes an installer in `dist\`.

---

## Notes
- Progress lives on the device it's installed on (localStorage). It doesn't sync.
- On Windows/Firefox/Electron the microphone is unavailable — type instead. On Android Chrome it works.
- Fonts come from Google when online and are cached for offline after the first load.
