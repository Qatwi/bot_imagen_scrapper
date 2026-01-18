# bot_imagen_scrapper



## 1) Short “About” (sidebar)

A thread-safe Python image scraper/downloader for booru-style sites, featuring parallel downloads, SQLite caching (URL/MD5/ETag dedupe), resume mode, advanced logging, optional proxy support, and optional AES-GCM encryption.

---

## 2) README intro + features

### 🖼️ Image Scraper & Downloader (Python)

This project is a **thread-safe scraper + downloader** built to collect and download large batches of images from **booru-style** websites via a simple **CLI**. It’s optimized for **high volume**, **low RAM usage**, and the ability to **resume interrupted runs** without wasting time reprocessing the same content.

**Key features**

* ✅ **SQLite cache** with:

  * configurable max entries (or unlimited)
  * automatic expiry by age (days)
  * CLI cache management (list / clear / history)
* ⚡ **Parallel downloads** using `ThreadPoolExecutor` (good for hundreds/thousands of files).
* 🧾 Full download tracking: **URL**, filename, **MD5**, size, timestamps, tag, and category.
* ♻️ **Resume mode** using a state file to continue interrupted sessions.
* 🧠 Duplicate prevention via **URL**, **MD5**, and signals like **ETag/Content-Length**.
* 📊 Structured logging + optional progress bar (`tqdm`).
* 🔐 Optional **AES-GCM encryption** for sensitive stored data (when enabled with a key).
* 🧩 Easy to extend: add new domains by defining site configs/selectors.

---

## 3) Responsible use disclaimer (recommended)

### Responsible use

This repository is intended for **educational**, **testing**, and **personal automation** purposes in authorized contexts. Please respect website **Terms of Service**, `robots.txt`, and copyright/licensing rules. Don’t use this tool to collect content you don’t have permission to access or store.

---

## Bonus: Portfolio tagline (1-liner)

A resilient image collection pipeline focused on **concurrency**, **deduplication**, **SQLite persistence**, and **fault tolerance** (resume + retries).

If you want, I can also write a clean **README “Usage” section** with safe example commands + a neat “CLI flags” list that matches your script exactly.
