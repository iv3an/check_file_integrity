<div align="center">
<pre>
██╗  ██╗ █████╗ ███████╗██╗  ██╗
██║  ██║██╔══██╗██╔════╝██║  ██║
███████║███████║███████╗███████║
██╔══██║██╔══██║╚════██║██╔══██║
██║  ██║██║  ██║███████║██║  ██║
╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝
       
</pre>



![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-292929?style=flat&logo=json&logoColor=white)
![Hashlib](https://img.shields.io/badge/Hashlib-SHA--256%20%2B%20MD5-16a085?style=flat)
![Colorama](https://img.shields.io/badge/CLI-Colorama-8b5cf6?style=flat)

</div>

### About

A small personal learning project I worked on to understand how hashing works and how it can detect file changes.

HASHWATCH saves a file’s **SHA-256 and MD5 hashes**, then compares them later to report **unchanged**, **modified**, or **missing** files.

### Demo

![HASHWATCH demo](/demo.png)

### Install & Run

Linux / WSL — requires Python 3, venv, and curl.

```bash
curl -fL https://github.com/iv3an/file_integrity/archive/HEAD.tar.gz -o hashwatch.tar.gz
mkdir -p hashwatch
tar -xzf hashwatch.tar.gz -C hashwatch --strip-components=1
cd hashwatch

python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python file_integrity_checker.py
```

If creating the virtual environment fails, install the venv package named in your terminal’s error message, then retry.

### How to Use

| Option | What it does |
| :---: | :--- |
| **1** | Save a baseline — enter file paths separated by commas |
| **2** | Check files against the saved baseline |
| **3** | View saved hashes and timestamps |
| **4** | Exit |

### Test It

Create a test file before launching:

```bash
echo "hello" > test.txt
```

Select **1**, enter `test.txt`, then select **2** → **UNCHANGED**.

In another terminal in the same folder:

```bash
echo "changed" >> test.txt
```

Select **2** again → **MODIFIED**.

```bash
mv test.txt test-backup.txt
```

Select **2** again → **MISSING**.

> Baselines are stored in `baseline.json`. Adding a file again replaces its baseline. Checks run only when you select option 2.
