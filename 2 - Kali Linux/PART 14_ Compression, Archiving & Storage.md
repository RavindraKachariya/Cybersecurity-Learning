# PART 14: Compression, Archiving & Storage

*(tar, gzip, bzip2, dd – Deep & Practical)*

In Linux security work, you constantly deal with:

- Large log files
- Scan results
- Evidence data
- Backups
- Disk images

Compression and archiving help you **store, move, hide, and analyze data efficiently**.

For hackers and forensic analysts, these tools are **not optional**.

---

## 1. Archiving vs Compression (Very Important Difference)

Many beginners confuse these two concepts.

### Archiving

- Combines **multiple files into one**
- Does **not reduce size by default**

### Compression

- **Reduces file size**
- Saves storage and bandwidth

Often, both are used **together**.

---

### Concept Flow

```
Multiple files
     │
     ▼
Archive (tar)
     │
     ▼
Compressed archive (gzip / bzip2)

```

---

## 2. `tar` – Tape Archive Tool

### What `tar` Does

`tar` is used to:

- Combine files and directories
- Preserve file structure
- Preserve permissions

It is the **most commonly used archiving tool** in Linux.

---

### Basic Syntax

```bash
tar [options] archive_name files

```

---

## 3. Creating an Archive with `tar`

### Example

```bash
tar -cvf backup.tar /etc

```

Explanation:

- `c` → create archive
- `v` → verbose (show progress)
- `f` → filename

This command:

- Archives the entire `/etc` directory
- Stores it as `backup.tar`

---

### Why Hackers Use This

- Backup configuration files
- Steal data in one file
- Preserve permissions for later use

---

## 4. Viewing Contents of a Tar Archive

```bash
tar -tvf backup.tar

```

This shows:

- Files inside the archive
- Without extracting them

Very useful during **forensic analysis**.

---

## 5. Extracting a Tar Archive

```bash
tar -xvf backup.tar

```

This:

- Restores files
- Preserves original structure

---

## 6. `gzip` – Fast Compression

### What `gzip` Does

`gzip` compresses files using:

- Fast algorithm
- Moderate compression ratio

It is widely used because it is:

- Quick
- Reliable
- Supported everywhere

---

### Compress a File

```bash
gzip report.txt

```

Result:

```
report.txt.gz

```

---

### Decompress a File

```bash
gunzip report.txt.gz

```

---

### Security Perspective

Hackers use `gzip` to:

- Compress stolen data
- Reduce transfer size
- Avoid detection by hiding content

---

## 7. Combining `tar` + `gzip` (Most Common Use)

### Create Compressed Archive

```bash
tar -czvf backup.tar.gz /etc

```

Options explained:

- `c` → create
- `z` → use gzip
- `v` → verbose
- `f` → filename

---

### Extract Compressed Archive

```bash
tar -xzvf backup.tar.gz

```

---

### Why This Is Important

Almost all:

- Backups
- Tool packages
- Exploit archives

use this format.

---

## 8. `bzip2` – Higher Compression

### What `bzip2` Does

`bzip2` provides:

- Better compression than gzip
- Slower speed

Used when:

- Storage matters more than speed

---

### Example

```bash
tar -cjvf backup.tar.bz2 /etc

```

---

### Security Perspective

Used in:

- Long-term storage
- Forensics archives
- Large evidence datasets

---

## 9. Understanding File Extensions

| Extension | Meaning |
| --- | --- |
| `.tar` | Archive only |
| `.gz` | gzip compressed |
| `.bz2` | bzip2 compressed |
| `.tar.gz` | tar + gzip |
| `.tar.bz2` | tar + bzip2 |

Knowing extensions prevents **extraction mistakes**.

---

## 10. `dd` – Disk Duplication Tool (VERY IMPORTANT)

### What `dd` Does

`dd` copies data **bit by bit**, not file by file.

It is used for:

- Disk imaging
- Forensics
- Backups
- Data destruction

⚠️ `dd` is extremely powerful and dangerous.

---

## 11. How `dd` Works (Concept Flow)

```
Input device/file
      │
      ▼
Bit-by-bitcopy
      │
      ▼
Output device/file

```

No understanding of filesystem required.

---

## 12. Creating a Disk Image with `dd`

### Example

```bash
ddif=/dev/sda of=disk.img

```

Explanation:

- `if` → input file (source disk)
- `of` → output file (image)

This creates a **forensic disk image**.

---

### Security & Forensics Perspective

`dd` is used to:

- Preserve evidence
- Clone compromised systems
- Analyze malware offline

This ensures:

- No modification of original data

---

## 13. Monitoring `dd` Progress

By default, `dd` shows no progress.

Better usage:

```bash
ddif=/dev/sda of=disk.img status=progress

```

---

## 14. Data Destruction with `dd` (Dangerous)

```bash
ddif=/dev/zero of=/dev/sda

```

This:

- Overwrites entire disk with zeros
- Destroys all data permanently

⚠️ **Never run unless you fully understand it**

---

## 15. Compression & Storage in Real Attacks

```
Collectdata
     │
tar → bundle
     │
gzip → compress
     │
Transfer / store

```

This is how:

- Data exfiltration works
- Evidence is archived
- Reports are prepared