<div align="center">

<!-- Logo emblem (SVG fallback inline) -->
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/DYNAMOSTUDIOS/WIKIMAPI-ARCHIVER/blob/main/wikimapia.org-logo.png" />
  <img src="https://github.com/DYNAMOSTUDIOS/WIKIMAPI-ARCHIVER/blob/main/wikimapia.org-logo.png" alt="Wikimapia Archiver Logo" height="250" />
</picture>

<h1>Wikimapia Archiver</h1>

<p><em>Preserve the world's geographic memory — before it disappears.</em></p>

<br/>

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-storage-003B57?style=flat-square&logo=sqlite&logoColor=white)
![GeoJSON](https://img.shields.io/badge/GeoJSON-export-brightgreen?style=flat-square)
![Status](https://img.shields.io/badge/status-work%20in%20progress-orange?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

</div>

---

## 🌍 About

[Wikimapia](https://wikimapia.org) is a collaborative mapping project containing **years of community-created geographic knowledge** that exists nowhere else:

| Data Type | Description |
|---|---|
| 🔷 Hand-drawn polygons | User-traced boundaries of places, districts, and landmarks |
| 📝 Local descriptions | Native-language annotations and cultural context |
| 🕰️ Historical locations | Places that may no longer exist in the physical world |
| 💬 Comments & annotations | Community discussions attached to map objects |
| 🏷️ User-generated metadata | Tags, categories, and custom attributes |

> **Some of this information may eventually disappear.**

This project aims to **archive and preserve** that data in open, structured, portable formats — so it can outlive the platform it was created on.

## 🚧 Project Status

> **⚠️ Work in Progress** — actively developed, not yet production-ready.

### ✅ Current Features

- [x] Polygon / BBOX geographic scanning
- [x] Wikimapia API integration
- [x] Object detail extraction
- [x] GeoJSON export
- [x] SQLite archival storage

### 🗺️ Planned Features

- [ ] Improved object discovery algorithms
- [ ] Photo & image archival
- [ ] Historical snapshots & diff tracking
- [ ] Visualization / render system
- [ ] Offline archive viewer (standalone app)

---

## 🎯 Goals

This project is built around a single mission: **geographic knowledge preservation**.

```
📦 Preserve geographic history
🛡️ Archive endangered metadata  
📐 Store polygon geometry
💾 Build portable offline archives
🌐 Protect community-generated geographic knowledge
```

We believe that place-knowledge created by real communities deserves to survive beyond the lifespan of any single platform.

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Runtime | Python 3.11+ |
| Storage | SQLite |
| Export format | GeoJSON |
| Data pipeline | Async scraping pipeline |
| Geometry | Polygon processing |
| Source | Wikimapia API |

---

## 🚀 Getting Started

### Prerequisites

```bash
python --version   # 3.11 or higher required
```

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/wikimapia-archiver.git
cd wikimapia-archiver

# Create a virtual environment
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Configuration

```bash
cp .env.example .env
# Edit .env and add your Wikimapia API key
```

```dotenv
# .env
WIKIMAPIA_API_KEY=your_api_key_here
OUTPUT_DIR=./archives
```

### Usage

```bash
# Scan a bounding box (lat_min, lon_min, lat_max, lon_max)
python archiver.py scan --bbox 41.0,28.9,41.1,29.0

# Export archived data to GeoJSON
python archiver.py export --format geojson --output ./output/istanbul.geojson

# View archive statistics
python archiver.py stats
```

---

## 📁 Project Structure

```
wikimapia-archiver/
├── archiver/
│   ├── __init__.py
│   ├── api.py            # Wikimapia API client
│   ├── scanner.py        # BBOX / polygon scanner
│   ├── extractor.py      # Object detail extractor
│   ├── storage.py        # SQLite archival layer
│   └── exporter.py       # GeoJSON / format exporters
├── assets/               # Logos, screenshots, banners
├── archives/             # Default output directory (gitignored)
├── tests/
├── .env.example
├── requirements.txt
└── README.md
```

---

## 🗄️ Data Formats

### GeoJSON Output

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Polygon",
        "coordinates": [[[28.97, 41.01], [28.98, 41.01], [28.98, 41.02], [28.97, 41.01]]]
      },
      "properties": {
        "id": 12345678,
        "title": "Hagia Sophia",
        "description": "Byzantine cathedral turned mosque...",
        "categories": ["religious", "historical"],
        "archived_at": "2025-01-15T10:30:00Z"
      }
    }
  ]
}
```

### SQLite Schema (simplified)

```sql
CREATE TABLE objects (
    id          INTEGER PRIMARY KEY,
    title       TEXT,
    description TEXT,
    geometry    TEXT,    -- GeoJSON polygon string
    tags        TEXT,    -- JSON array
    archived_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

---

## 🤝 Contributing

Contributions are welcome! This is a preservation project — every improvement matters.

```bash
# Fork the repo, then:
git checkout -b feature/your-feature-name
git commit -m "feat: describe your change"
git push origin feature/your-feature-name
# Open a Pull Request
```

Please open an issue first for major changes. Bug reports, feature suggestions, and documentation improvements are all appreciated.

---

## 📜 Disclaimer

> This project is intended **for archival and research purposes only**.
>
> It is **not affiliated with, endorsed by, or connected to Wikimapia** in any way.
> Please use responsibly and in accordance with Wikimapia's terms of service.
> Archived data should not be republished commercially.

---

## 📄 License

MIT License — see [`LICENSE`](./LICENSE) for details.

---

<div align="center">

**Built with care for the places people love — and the memories attached to them.**

<br/>

⭐ Star this repo if you believe geographic knowledge is worth preserving.

</div>
