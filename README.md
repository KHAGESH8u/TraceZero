 ---
 # 🛡️ TraceZero Sentinel 


**An automated, multi-modal forensic metadata sanitization engine.**

Every time a user shares a photo, document, or archive, they unknowingly leak invisible data—GPS coordinates, camera serial numbers, author identities, exact creation timestamps, and hidden OS trackers.

**TraceZero** is a privacy firewall that intercepts these files, strips them of hidden tracking data, and rebuilds them so you can share your work **without sharing your footprint.**

---

# ✨ Key Features

### 🖥️ Three Modes of Operation

**Interactive GUI**
- Dracula-themed dashboard
- Real-time risk scoring
- Visual forensic breakdown

**Global CLI**
- Run from any terminal
- Fast headless sanitization
- Perfect for automation

**Background Sentinel**
- System tray daemon
- Watches folders continuously
- Automatically sanitizes files in milliseconds

#

### 🧹 Deep Structural Sanitization

TraceZero doesn't just mask metadata.

It performs **true structural cleaning** including:

- Pixel re-encoding for images
- Unix Epoch timestamp resets (1970)
- XML metadata removal in documents
- Archive reconstruction

This ensures **no hidden metadata survives.**

#

### 📊 Forensic Auditing

- Calculates a **Risk Score (0–100)** based on exposed metadata
- Shows forensic breakdown of detected traces
- Logs all actions to a **local serialized history manager**

#

### 📄 PDF Reporting

Generate **professional offline forensic audit reports** that include:

- Metadata traces discovered
- Risk analysis
- Sanitization results
- Timestamped reports for documentation

 ---

# 🧠 Threat Model

TraceZero Sentinel protects against **unintentional metadata leaks** when sharing files online.

Examples of exposed forensic data include:

- GPS coordinates embedded in images
- Camera device identifiers
- Author names in documents
- Creation timestamps
- Software fingerprints
- OS-generated tracker files (.DS_Store, Thumbs.db)

Attackers, investigators, or automated scraping systems can use this metadata to identify:

- the file creator
- the device used
- the location where the file was created
- editing history

TraceZero removes these traces before files are distributed.

---

# 🗂️ Supported File Types

| Format | Sanitization Protocol |
|------|-----------------------|
| **JPG / PNG** | Raw pixel read + re-encoding to remove EXIF/XMP headers |
| **ZIP** | Extract → delete OS trackers → rebuild archive |
| **PDF** | Remove author, creation date, software metadata |
| **DOCX** | Remove revision history + creator identity |

#### More Format Support In future releases

---

# 🚀 Quick Start & Installation

## Prerequisites

- **Java 17+**
- **Maven**

## Build from Source

### 1️⃣ Clone the repository

```bash
git clone https://github.com/yourusername/TraceZero.git
cd TraceZero
```
### 2️⃣ Build the project

```bash
mvn clean package
```
### 3️⃣ Locate the compiled JAR

-  Navigate to the target directory.

 - You will find:

    ```hellofx-1.0-SNAPSHOT-shaded.jar```

  - Rename it to:

    ```tracezero.jar```

---

# ⚙️ Windows Global Setup (Optional)

### To run TraceZero from any command prompt:

  - Move these files into a permanent folder named

    ```C:\TraceZero```

  - Required files:

     - ```tracezero.jar``` (From Previous Step)
     - ```tracezero.bat``` (Code as Follws:)
       
       ```bash
          @echo off
          java -jar "C:\TraceZero\tracezero.jar" %*
       ```
     - ```install_tracezero.bat```  (Code as Follws:)
       ```bash
          @echo off
          setlocal
          set "targetDir=%~dp0"
          :: Remove the trailing backslash if it exists
          if "%targetDir:~-1%"=="\" set "targetDir=%targetDir:~0,-1%"
          
          echo [!] TRACEZERO SENTINEL: Initializing Global Access...
          echo Target Directory: %targetDir%
          
          :: Use setx to add the current folder to the USER path (No Admin Needed)
          setx PATH "%PATH%;%targetDir%" >nul
          
          echo.
          echo [✓] SUCCESS: TraceZero is now global.
          echo [i] Please RESTART your terminal/CMD window to use the command.
          echo.
          echo Try typing 'tracezero' from any folder to launch.
          pause
       ```

  - Run:

    ```bash 
    install_tracezero.bat
    ```

  - Open a new terminal

- Run:

    ```bash
    tracezero
    ```
---

# 💻 Usage

  - Launch GUI Dashboard
    ```bash
       tracezero
    ```
    
  - CLI Sanitization
    ```bash
       tracezero "C:\Path\To\Your\secret_document.docx"
    ```
    
### TraceZero will:

  - Scan the file

  - Display forensic metadata in terminal

  - Remove all traces

  - Save a sanitized copy in the same directory

---

# 🛠️ Tech Stack

### Language

  - Java 17

  - Framework

  - JavaFX

### Build Tool

  - Maven

### Core Libraries

  - metadata-extractor → Image metadata analysis

  - Apache PDFBox → PDF metadata parsing

  - Apache POI → Word document manipulation

---

# 🔒 Security Philosophy

TraceZero is built on a zero-trust metadata model.

If a file contains metadata, it is treated as potentially sensitive forensic evidence and removed during reconstruction.

The goal is simple:

Share files, not fingerprints.

---

# 📜 License

This project is open source and available under the MIT License.

---

# 🏆 Hackathon Project

Built for CODE-A-THON 2.0, MAR 2026, VIT, WADALA, MUMBAI, MAHARASHTRA
