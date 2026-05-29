
---

## 🔧 APIs & Libraries Used

| Feature | API / Library | Key Required? |
|---------|---------------|----------------|
| Quran text & translation | [AlQuran Cloud](https://alquran.cloud) | No |
| Quran audio | Islamic Network CDN (Alafasy) | No |
| Hadith | [fawazahmed0/Hadith-API](https://github.com/fawazahmed0/hadith-api) (jsDelivr CDN) | No |
| Prayer times & Qibla | [Aladhan API](https://aladhan.com) | No |
| Mosque locations | OpenStreetMap + Overpass API | No |
| Geo address → coordinates | Nominatim (OSM) | No |
| Moon phase | Local calculation (synodic cycle) | – |
| Map display | Leaflet.js + CartoDB tiles | No |
| Charts | Chart.js | – |

**No API keys are required** – all services are free and publicly accessible.

---

## 🧩 Module Walkthrough

### 1. Quran
- Select surah from dropdown, choose translation, click **Load Surah**.
- Click ▶️ to play recitation for any verse.
- Use the search box to find English keywords across the Quran.

### 2. Hadith
- Choose a collection via sub‑tabs.
- Enter a keyword (e.g., *mercy*, *prayer*) and click **Search**.
- **Random** fetches a random hadith from the selected collection.
- Results display English translation, Arabic text (if available), grade (Sahih/Hasan/Da‘if), and narrator.

### 3. Faraid (Inheritance)
- Expand categories: Pasangan & Anak, Ibu Bapa & Datuk Nenek, Adik-beradik.
- Enter the number of heirs in each category (0 if not applicable).
- Click **Kira Sekarang** – the shares table, percentages, and pie chart update automatically.
- The calculator handles ‘awl (increase) and radd (return) correctly according to Syafi‘i school.

### 4. Prayer & Qibla
- Enter city/country or click **My Location** to get prayer times.
- **Next prayer** is highlighted.
- Hijri date is shown below the prayer grid.
- Click **Allow Notifications** to grant permission; then whenever you fetch prayer times, notifications are scheduled for Fajr, Dhuhr, Asr, Maghrib, Isha.
- For Qibla: enter your coordinates (or use “My Location” in prayer section) and click **Calculate** – see degrees, cardinal direction, and animated compass.

### 5. Masjid Finder
- Click **Gunakan Lokasi Saya** – after granting location permission, it shows your position on the map and searches for mosques within 2 km.
- Click **Cari Dalam 2km** to repeat the search at the current map center.
- Each mosque appears in the list with a **Peta** button to zoom to its location.

### 6. Asma Al-Husna
- Click **Show Random Name** – displays one of the 99 Names with Arabic, transliteration, and meaning.
- Click **Show All 99** – displays all names in a responsive grid.

### 7. Moon Phase
- Automatically shows today’s moon phase, emoji, illumination percentage, lunar day, and days until the next full/new moon.

### 8. Geo Info
- Enter an address (e.g., *Masjid Negara, Kuala Lumpur*) and click **Get Coordinates**.
- Returns latitude, longitude, and full display name from OpenStreetMap.
- Use **Copy Coordinates** or **→ Use for Qibla** to send coordinates directly to the Qibla calculator.

---

## ⚙️ Customization

| What to change | Where in code |
|----------------|----------------|
| Default city for prayer times | `cityInput` value in HTML (e.g., `value="Kuala Lumpur"`) |
| Prayer calculation method | Change `method=2` in `getPrayerByCity()` and `getPrayerByLocation()` – see [Aladhan methods](https://aladhan.com/prayer-times-api#method) |
| Hadith collections | Modify the sub‑tabs in HTML and the mapping in `selectCollection()` |
| Asma names list | Edit the `asmaNames` array (full 99 included) |
| Moon phase emoji mapping | Inside `renderMoon()` function |
| Quran reciter | Replace the audio URL base in `playVerse()` |
| Mosque search radius | Change `around:2000` (meters) in the Overpass query |

---

## 📱 Browser & Device Support

- Works on **desktop**, **tablet**, and **mobile** browsers.
- Responsive layout adapts to small screens.
- Requires JavaScript enabled.
- Geolocation and Notifications require user permission (prompted when used).

---

## ❗ Troubleshooting

| Issue | Likely fix |
|-------|-------------|
| Quran surah not loading | Check internet connection; the AlQuran Cloud API may be temporarily slow – retry. |
| Hadith search returns no results | Try a broader keyword; some collections have fewer hadiths. |
| Prayer times error (“bandar tidak ditemui”) | Use a major city name (e.g., “Kuala Lumpur” instead of a small village). |
| Notifications not working | Click **Allow Notifications** first; also check your browser’s site settings. |
| Mosque map not showing | Click **Gunakan Lokasi Saya** – the map needs coordinates. If location denied, you cannot use this feature. |
| Geo address not found | Use a well‑known landmark or city; avoid vague terms. |

---

## 🤝 Credits

- **Quran API** – [AlQuran Cloud](https://alquran.cloud)
- **Hadith API** – [fawazahmed0/Hadith-API](https://github.com/fawazahmed0/hadith-api)
- **Prayer Times & Qibla** – [Aladhan API](https://aladhan.com)
- **Map & Tiles** – [Leaflet](https://leafletjs.com) + [CartoDB](https://carto.com/)
- **Mosque Data** – [OpenStreetMap](https://www.openstreetmap.org) via Overpass API
- **Geo Coding** – [Nominatim](https://nominatim.openstreetmap.org)
- **Charts** – [Chart.js](https://www.chartjs.org/)

---

## 📄 License

**MIT** – free to use, modify, and distribute. Attribution appreciated but not required.

---

*Built with 🌙 for the global Muslim community.*  
**“And We have certainly made the Quran easy for remembrance.”** (Qur'an 54:17)
