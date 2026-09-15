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

### Quick test

Add a test file → edit it → check for `MODIFIED`.
Delete it → check for `MISSING`.

Checks run on demand. Keep your baseline trusted. Set `NO_ANIMATION=1` to disable the startup animation.
