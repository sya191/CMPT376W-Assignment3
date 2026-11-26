# LogLens

LogLens is a local, command-line Python script (`loglens.py`) for counting records in a CSV log file by log level.

* **Local only:** LogLens runs entirely on your computer and does not transmit, upload, or store your data externally.
* **Read-only:** It reads your CSV file without modifying, repairing, or rewriting it.
* **Scope:** It counts matching records; it does not diagnose system failures.

## Requirements

* **Python 3.10 or newer**
* Only the Python standard library is used (no third-party packages are required).
* Basic familiarity with CSV files and using a terminal (written for computing students and new technical interns; no prior experience with LogLens is required).

For step-by-step instructions on downloading the repository and verifying your setup, see [docs/INSTALL.md](docs/INSTALL.md).

## Input format

LogLens expects a CSV file with column headers named **exactly**:

* `timestamp`
* `level`
* `message`

Accepted values for the `level` column are uppercase `INFO`, `WARN`, and `ERROR`. A sample input file is included at `data/sample_logs.csv`.

## Using the program

Open a terminal in the **repository root** (the folder containing `loglens.py`). The examples below use `python`; on some systems, the launcher is `python3` or `py` instead.

### Count records for a specific log level

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```

Expected output:

```text
Records matching ERROR: 2
```

### Count all records

Omit the optional `--level` argument to count every record in the file:

```bash
python loglens.py --file data/sample_logs.csv
```

Expected output:

```text
Records matching ALL: 6
```

### Command-line options

To view all supported arguments and options:

```bash
python loglens.py --help
```

* `--file` *(required)*: Path to the input CSV log file.
* `--level` *(optional)*: Filter count by `INFO`, `WARN`, or `ERROR`.

## Reporting issues

If you run into a problem, check [docs/INSTALL.md](docs/INSTALL.md) for troubleshooting steps first. When opening an issue, include your Python version, the command you ran, the error message, and a minimal, **sanitized** reproducible example. **Do not post private or sensitive log data publicly.**
