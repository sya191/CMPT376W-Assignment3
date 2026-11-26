# LogLens Installation and Setup Guide

This guide walks you through downloading LogLens, navigating to the repository root, and verifying that the script runs on your computer. For full usage details and CSV formatting rules, see [README.md](../README.md).

## Prerequisites

* **Python 3.10 or newer**
* A terminal

LogLens runs locally using only the Python standard library. No third-party dependencies or internet connection are needed once you have the repository files.

To check your Python version, run:

```bash
python --version
```

> **Note:** On some computers, the Python launcher is `python3` or `py` instead of `python`. Use whichever command reports Python 3.10 or newer.

## 1. Get the repository files

1. Download or clone the repository from GitHub (for example, select **Code → Download ZIP** and extract the archive, or clone it with `git`).
2. Note the location of the extracted or cloned project folder.

## 2. Navigate to the repository root

Open a terminal and change into the **repository root**. This is the top-level folder that contains `loglens.py`:

```bash
cd path/to/CMPT376W-Assignment3
```

Make sure `loglens.py` and the `data/` directory are present in this folder before running commands.

## 3. Verify your setup

Run LogLens against the included sample log file (`data/sample_logs.csv`) to confirm everything works:

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```

Expected output:

```text
Records matching ERROR: 2
```

You can also omit the optional `--level` flag to count all records in the sample file:

```bash
python loglens.py --file data/sample_logs.csv
```

Expected output:

```text
Records matching ALL: 6
```

To view all valid command-line options:

```bash
python loglens.py --help
```

Once verification succeeds, see [README.md](../README.md) for required CSV column headers and general usage.

## Troubleshooting

* **`python` is not recognized or shows an older version:** Try `python3` or `py` instead, and confirm that Python 3.10 or newer is installed.
* **`File not found` error:** Confirm that your terminal is in the repository root (where `loglens.py` is located) and check the spelling and path of the `--file` argument.
* **CSV column or level errors:** Refer to [README.md](../README.md) for the exact required headers and uppercase level values.
* **Still stuck?** Confirm your Python version, the exact command you ran, and the error message before opening an issue. Include a problem description and a minimal, **sanitized** reproducible example. **Do not attach raw log files or post private or sensitive data publicly.**
