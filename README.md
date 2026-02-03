# 🖼️ Image Scraper & Downloader (Python)

A **high-performance, thread-safe image scraper and downloader** designed for collecting large volumes of images from **booru-style websites** via a clean and flexible **CLI interface**.

The project is optimized for **scalability**, **low memory usage**, and **fault tolerance**, allowing interrupted runs to be resumed without reprocessing already downloaded content.

---

## 🚀 Features

### 🔹 Caching & Persistence

* **SQLite-based cache** with:

  * Configurable maximum entries (or unlimited mode)
  * Automatic expiration by age (days)
  * CLI tools for cache inspection and maintenance:

    * list entries
    * clear cache
    * view download history
* Persistent metadata storage for long-term tracking and analysis.

---

### 🔹 Performance & Concurrency

* ⚡ **Parallel downloads** powered by `ThreadPoolExecutor`

  * Efficient for hundreds or thousands of images per run
  * Designed to minimize RAM usage during high-volume operations
* Thread-safe architecture to prevent race conditions and data corruption.

---

### 🔹 Reliability & Resume Support

* ♻️ **Resume mode** via a state file:

  * Safely continues interrupted sessions
  * Avoids re-fetching or re-downloading previously processed files
* Robust error handling with retries and structured logging.

---

### 🔹 Duplicate Detection & Integrity

* Multi-layer duplicate prevention using:

  * URL matching
  * **MD5 hash** comparison
  * HTTP signals such as **ETag** and **Content-Length**
* Ensures storage efficiency and avoids redundant downloads.

---

### 🔹 Metadata & Logging

* Full download tracking, including:

  * Source URL
  * Filename
  * File size
  * MD5 checksum
  * Timestamps
  * Tags and categories
* 📊 Structured logging with adjustable verbosity
* Optional progress visualization using `tqdm`.

---

### 🔹 Security (Optional)

* 🔐 **AES-GCM encryption** support for sensitive stored data

  * Enabled via user-provided encryption key
  * Designed for environments where metadata confidentiality matters

---

### 🔹 Extensibility

* 🧩 Easy to extend to new sites:

  * Add support by defining site-specific configs and selectors
* Clean separation between core logic and site adapters.

---

## 📦 Use Cases

* Dataset collection for research or ML experiments
* Personal archiving and automation
* Performance testing of concurrent download systems
* Learning resource for thread-safe scraping architectures

---

## ⚠️ Responsible Use Disclaimer

### Responsible Use

This repository is intended for **educational**, **testing**, and **personal automation** purposes **only**, and must be used in **authorized contexts**.

Users are responsible for ensuring compliance with:

* Website **Terms of Service**
* `robots.txt` directives
* Copyright and licensing restrictions

Do **not** use this tool to collect, store, or redistribute content without proper permission.
The author assumes no responsibility for misuse or violations resulting from the use of this software.

---

Si quieres, en el siguiente paso puedo ayudarte a:

* 🔹 añadir una sección **Installation / Usage**
* 🔹 escribir **CLI examples** bien pro
* 🔹 o dejar un **README orientado a portfolio** (pensado para recruiters)

Dime hacia dónde lo quieres llevar 👌



