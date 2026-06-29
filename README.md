
---

# Image Bot v_01 🖼️

GUI-Based Automatic Image Scraper & Downloader (Python)

**Image Bot** is a **desktop application with a graphical user interface (GUI)** that automatically searches, filters, and downloads batches of images based on a simple user query.

The application is designed to be **easy to use** (no command-line interaction required for normal users) while internally providing a **robust and scalable scraping engine** with caching, deduplication, concurrency, and optional advanced features.

---

## Overview

Image Bot focuses on **automation, reliability, and usability**.
All functionality is controlled through the graphical interface, making it suitable for non-technical users while still implementing professional-grade internal logic.

The GUI handles search, download execution, progress reporting, and logging in real time.

---

## Graphical User Interface

The application launches a **Tkinter-based desktop interface** that includes:

* A single search input (what image you want)
* A numeric field for the number of images
* An output directory selector
* A live terminal-style log window
* Start / Stop / Clear controls

No manual commands are required to operate the application.
![image alt](https://github.com/Qatwi/bot_imagen_scrapper/blob/059ed757a493282a96c6ad64c00311057e329c75/Screenshot_20260629_153829.png)
---

## Automatic Image Search

When a search term is entered (for example: `cats`, `landscapes`, `anime`), the bot automatically:

1. Detects the search category using keyword analysis
2. Selects the most appropriate image source
3. Falls back to Wikimedia Commons for general queries
4. Filters out low-quality, irrelevant, or duplicate images
5. Downloads images concurrently
6. Prevents re-downloads using a persistent cache

---

## Key Features ⚙️

### Performance

* Multi-threaded downloads using `ThreadPoolExecutor`
* Streaming downloads to minimize memory usage

### Deduplication

* URL-based cache
* ETag / Content-Length checks (when available)
* MD5 hash verification after download

### Persistent Cache

* SQLite database storing:

  * image URL (optionally encrypted)
  * filename
  * file size
  * MD5 hash
  * timestamps
  * tag and category

### Resume-Ready Architecture

* Internal state tracking to avoid reprocessing
* Designed to handle interruptions safely

### Optional Encryption

* AES-GCM encryption for sensitive stored values
* Enabled only when a user-provided key is supplied

### Extensible Design

* New image sources can be added via configuration dictionaries
* Clear separation between GUI logic and scraping logic

---

## Installation

### Requirements

* Python 3.10 or newer recommended

Core dependencies:

* `requests`
* `beautifulsoup4`

Optional dependencies:

* `tqdm` (progress indicators)
* `cloudscraper` (Cloudflare-protected sites)
* `cryptography` (AES-GCM encryption)
* `tkinter` (GUI, often bundled with Python)

### Setup

```bash
git clone https://github.com/Qatwi/bot_imagen_scrapper.git
cd bot_imagen_scrapper
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Example `requirements.txt`:

```txt
requests
beautifulsoup4
tqdm
cloudscraper
cryptography
```

---

## Running the Application

### GUI Mode (default)

```bash
python3 bot_imagen.py
```

If Tkinter is available, the graphical interface will launch automatically.
If not, the application will gracefully fall back to console mode.

---

## Output Structure

Downloaded images are organized automatically as:

```
<output_directory>/<search_term>/
```

Example:

```
downloads/cute_cats/
```

---

## Local Data Files

The application creates and maintains the following local files:

* `scraper_cache.db` — SQLite cache and download history
* `scraper_config.json` — persistent configuration
* `scraper_state.json` — internal resume/state data

These files allow the application to avoid duplicates and maintain consistency across runs.

---

## Responsible Use

This software is intended for **educational**, **testing**, and **personal automation** use in **authorized contexts only**.

Users are responsible for complying with:

* Website Terms of Service
* `robots.txt` directives
* Copyright and licensing rules

The author assumes no responsibility for misuse.

---

## Project Status

This project is actively evolving and serves as:

* a practical personal automation tool, and
* a portfolio project demonstrating GUI integration, scraping architecture, caching, and concurrency.


