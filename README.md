# statementpdftocsv

Python utility for converting statement PDFs in a local folder into CSV exports with a checksum comparison.

## Requirements

- Python 3
- Java available for `tabula-py`
- Input PDF statements placed in the configured source folder

## Dependencies

Install the required Python packages with:

```bash
pip install -r requirements.txt
```

## Usage

The current script expects statement PDFs in:

```text
C:\Satements
```

Then run:

```bash
python main.py
```

## Current behavior

The script:

1. Scans the configured folder for PDF files.
2. Extracts statement tables with `tabula`.
3. Writes CSV output for each PDF.
4. Reads the final page for totals.
5. Compares a calculated checksum with the extracted statement total.

## Maintenance notes

- The input path is currently hard-coded.
- The parsing logic assumes a very specific PDF layout and column layout.
- A future hardening pass should parameterize paths, add sample fixtures, and split parsing logic into testable functions.
