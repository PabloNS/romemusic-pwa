# RomeMusic

**RomeMusic** is a web application (PWA) that plays music associated with historical locations based on the user's location. When you approach a site, the app automatically plays the song assigned to that location.

This project works **entirely on the frontend** using HTML, JavaScript, and a `placesongs.json` file containing song information and coordinates. No backend is required.

---

## 📁 File Structure

```
/
├─ index.html               # Main page
├─ placesongs.json          # Song database with coordinates
├─ songs/                   # Folder with mp3 files
│   ├─ Gladiators.mp3
│   ├─ MarketsAndCircusses.mp3
│   └─ Imperium.mp3
│   └─ ...
├─ icons/
│   └─ favicon.png
├─ manifest.json            # Manifest for PWA
```

> Make sure that the names in `placesongs.json` exactly match the files in the `/songs/` folder.

---

## ⚙️ `placesongs.json` Example

```json
[
  {"latitude":41.8902502730118,"longitude":12.49219664304733,"locationName":"Colosseo","songName":"Gladiators.mp3"},
  {"latitude":36.721191613652636,"longitude":-4.416820127047902,"locationName":"Teatro Romano de Málaga","songName":"MarketsAndCircusses.mp3"},
]
```

> You can add as many entries as you want. The app selects the **closest song** to the user within a configurable range (`maxDistance` in meters).

---

## 🚀 How It Works

1. The user opens the app and clicks **Start**.
2. The app requests the user's location.
3. It calculates the distance between the user's position and each location in `placesongs.json`.
4. The nearest song within the maximum distance is selected.
5. The song automatically plays.
6. The app updates the on-screen status with:

    * Song name
    * Location name

---

## 🎵 Audio Playback

* MP3 files must be placed in the `/songs/` folder.
* The browser must allow audio playback.
* For mobile devices, installing as a PWA improves the experience and allows offline access.
* Autoplay policy: **the user must click Start first** to enable playback.

---

## 🌍 PWA and Mobile Support

* Compatible with installation as a **PWA**.
* The install button appears automatically on supported browsers.
* On iOS, the app displays instructions for adding it to the home screen.

---

## 🔧 Setup Instructions

1. Place all MP3 files in the `/songs/` folder.
2. Update `placesongs.json` with your locations and songs.
3. Open `index.html` in a modern web browser.
4. Click **Start** and allow geolocation access.
5. The app will play the song corresponding to the nearest location.

> Optional: Adjust the `maxDistance` variable in the script to define the maximum range for activating songs.

---

## 📑 Notes

* Ideal for demos, museums, tourist routes, or gamifying historical locations.
* Fully frontend: all logic and data are handled in the browser.
* Offline capable if installed as a PWA and MP3 files are cached.

---