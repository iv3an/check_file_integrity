<div align="center">
<pre>
 ██╗  ██╗ █████╗ ███████╗██╗  ██╗
 ██║  ██║██╔══██╗██╔════╝██║  ██║
 ███████║███████║███████╗███████║
 ██╔══██║██╔══██║╚════██║██╔══██║
 ██║  ██║██║  ██║███████║██║  ██║
 ╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝
       W  A  T  C  H
 ─────────────────────────────────
   [#] EVERY BYTE HAS A FINGERPRINT
       BASELINE · VERIFY · DETECT
</pre>
</div>

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-292929?style=flat&logo=json&logoColor=white)
![SHA-256 + MD5](https://img.shields.io/badge/hashlib-SHA--256%20%2B%20MD5-16a085?style=flat)
![Colorama](https://img.shields.io/badge/CLI-Colorama-8b5cf6?style=flat)



</div>

Python tool that detects file changes using SHA-256 and MD5 hashes. It compares files against a saved baseline to identify modified, missing, or unchanged files useful for checking important files for unexpected changes.


### Run

```bash
pip install -r requirements.txt
python file_integrity_checker.py
```

Python 3 required. Colorama adds terminal colors and is optional.

### Controls

| Option | Action |
| :---: | :--- |
| **1** | Add files to the baseline |
| **2** | Detect unchanged, modified, or missing files |
| **3** | View saved hashes and timestamps |
| **4** | Exit |

### Under the hood

Reads files in **4096-byte chunks**, calculates **SHA-256 + MD5**, and saves fingerprints in `baseline.json`. Both hashes must match. Adding a file again updates its baseline.

### Install & Run

On Linux / WSL, with Python 3 and curl installed:

```bash
# Download the project
curl -fL https://github.com/iv3an/file_integrity/archive/HEAD.tar.gz -o hashwatch.tar.gz
mkdir -p hashwatch
tar -xzf hashwatch.tar.gz -C hashwatch --strip-components=1
cd hashwatch

# Set up and install
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# Launch
python file_integrity_checker.py
```

### How to use

1. Select **1** and enter file paths separated by commas to save their hashes.
2. Select **2** to check for **UNCHANGED**, **MODIFIED**, or **MISSING** files.
3. Select **3** to view your saved baseline.
4. Select **4** to exit.

**Quick demo:** Run `echo "hello" > test.txt`, add `test.txt` with option **1**, then run `echo "changed" >> test.txt` in another terminal in the same folder. Select **2** to detect the change.
