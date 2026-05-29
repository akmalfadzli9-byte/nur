```markdown
# 🌙 Noor – Islamic Platform (with fawazahmed0 Hadith API)

A comprehensive Islamic web application featuring **Quran** (with recitation & search), **Hadith** (using [fawazahmed0/Hadith-API](https://github.com/fawazahmed0/hadith-api)), **Prayer Times**, **Qibla direction**, **Asma Al‑Husna** (99 Names of Allah), **Moon Phase**, and **Geo location** – all in a single, responsive HTML file.

## ✨ Features

| Module | Description | API / Source |
|--------|-------------|---------------|
| 📖 **Quran** | Browse surahs, Arabic + translation, verse‑by‑verse audio (Alafasy), keyword search | [AlQuran Cloud](https://alquran.cloud) |
| 🕊️ **Hadith** | Search/random from 6 major collections (Bukhari, Muslim, Abu Dawud, Tirmidhi, Nasai, Ibn Majah) with **grading** and **narrator** | [fawazahmed0/Hadith-API](https://github.com/fawazahmed0/hadith-api) – reliable, no API key |
| 🕌 **Prayer Times** | By city/country or geolocation; next prayer highlight; Hijri date | [Aladhan API](https://aladhan.com) |
| 🧭 **Qibla** | Degrees + animated compass from any coordinates | Aladhan API |
| ✨ **Asma Al‑Husna** | 99 Names of Allah – random or all names, Arabic, transliteration, meaning | **Embedded static JSON** (always works, offline) |
| 🌙 **Moon Phase** | Current phase, illumination %, lunar day, days to full/new moon | Client‑side calculation |
| 🌍 **Geo Info** | Address → coordinates (lat/lon) using OpenStreetMap | [Nominatim](https://nominatim.openstreetmap.org) – free, no key |

## 🚀 Getting Started

1. Save the code as `index.html` (or any name ending with `.html`)
2. Open in any modern browser (Chrome, Firefox, Safari, Edge)
3. No server, no build step, no API keys required
4. Internet connection needed for Quran, Hadith, Prayer, Qibla, and Geo

## 📁 File Structure

```
noor-islamic-platform/
├── index.html      # Complete application (HTML/CSS/JS)
└── README.md       # This file
```

## 🧩 How Each Module Works

### 📖 Quran
- Surah list loaded from AlQuran Cloud API
- Choose translation (Sahih International, Pickthall, Yusuf Ali)
- Click ▶ to play recitation (Sheikh Al‑Afasy)
- Search English text across the whole Quran

### 🕊️ Hadith (fawazahmed0 API)
- Uses pre‑downloaded JSON files from **jsDelivr CDN** (no API key, fast, CORS‑friendly)
- Select collection via sub‑tabs
- Enter a keyword (e.g., *mercy*, *prayer*) – searches both English and Arabic
- **Random** hadith button fetches a random hadith from the selected collection
- Results include:
  - English translation
  - Arabic text (if available)
  - Grade (Sahih/Hasan/Da‘if) with color coding
  - Narrator name
  - Reference

### 🕌 Prayer & Qibla
- **Prayer times**: by city/country or using geolocation
- Next prayer automatically highlighted
- Hijri date displayed
- **Qibla**: enter coordinates manually or get from Geo tab → degrees + rotating compass

### ✨ Asma Al‑Husna
- Completely offline – 99 names embedded in the script
- **Random Name** button picks one
- **Show All 99** displays full grid

### 🌙 Moon Phase
- Calculated locally using the lunar cycle formula (synodic period 29.53 days)
- Shows emoji, phase name, illumination %, lunar day, and days until full/new moon

### 🌍 Geo Info
- Type any address (e.g., *Medina, Saudi Arabia*)
- Uses **Nominatim (OpenStreetMap)** – free, no rate limits (but be polite)
- Returns coordinates + display name
- Buttons to copy coordinates or apply them directly to Qibla calculator

## 🔧 Hadith API Details (fawazahmed0)

This platform uses the excellent [fawazahmed0/Hadith-API](https://github.com/fawazahmed0/hadith-api) project, which provides authentic hadith collections in JSON format. We fetch the data from the jsDelivr CDN:

```
https://cdn.jsdelivr.net/gh/fawazahmed0/hadith-api@1/editions/eng-{collection}.min.json
https://cdn.jsdelivr.net/gh/fawazahmed0/hadith-api@1/editions/ara-{collection}.min.json
```

**Benefits:**
- No API key required
- Fast, reliable, CORS-enabled
- Includes both English translation and Arabic text
- Contains grading and narrator information
- Works offline after first load (cached)

**Collections supported:**
- `bukhari`
- `muslim`
- `abudawud`
- `tirmidhi`
- `nasai`
- `ibnmajah`

## ⚙️ Customization Tips

| What to change | Where |
|----------------|-------|
| Quran reciter | In `playVerse()` – replace audio base URL |
| Prayer calculation method | Change `method=2` in Aladhan calls ([list of methods](https://aladhan.com/prayer-times-api#method)) |
| Default city/country | `cityInput` and `countryInput` values |
| Asma names array | Edit `asmaNames` in the script section |
| Hadith collections | Modify the sub‑tabs in HTML and collection mapping in `selectCollection()` |
| Moon phase emoji mapping | Inside `renderMoon()` function |
| Colors & fonts | CSS `:root` variables |

## 🌐 API References (all work without keys)

- **Quran**: [https://alquran.cloud/api](https://alquran.cloud/api)
- **Hadith**: [https://github.com/fawazahmed0/hadith-api](https://github.com/fawazahmed0/hadith-api)
- **Prayer / Qibla / Hijri**: [https://aladhan.com](https://aladhan.com)
- **Geo (address → coordinates)**: [https://nominatim.org](https://nominatim.org)

## ❗ Troubleshooting

| Issue | Likely fix |
|-------|-------------|
| Quran search returns nothing | Use English keywords, e.g., "mercy", "paradise" |
| Hadith search returns no results | Try a broader keyword; some collections have fewer hadiths; ensure you've selected a valid collection |
| Hadith not loading at all | Check your internet connection; the jsDelivr CDN should be accessible globally |
| Prayer times not found | Use a major city (e.g., "Cairo" instead of a small village) |
| Geolocation denied | Allow location in your browser or enter city manually |
| Audio does not play | Some networks block the CDN; try a different verse or check connection |
| Qibla needle doesn't rotate | Make sure coordinates are valid and click "Calculate" again |

## 📄 License

**MIT** – free to use, modify, and share.

---

*Built with 🌙 for the global Muslim community.*  
**“And We have certainly made the Quran easy for remembrance.”** (Qur'an 54:17)
```
