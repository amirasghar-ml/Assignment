# Assignment

Simple Streamlit app for uploading CSV tables, preprocessing them, and using PandasAI to generate a combined answer table from a natural-language prompt.

## Features

- Upload up to 3 CSV files from the sidebar:
  - `Table1` (required)
  - `Table2` (required)
  - `Template table` (optional)
- Runs preprocessing to normalize key columns between `Table1` and `Table2`.
- Uses `SmartDatalake` with an OpenAI-backed LLM to produce result tables.
- Displays the generated result table and the last executed PandasAI code.

## Requirements

- Python 3.10+ recommended
- Dependencies listed in `requirements.txt`
- OpenAI/PandasAI environment variables in `.env`

Current `requirements.txt` contains:

- `streamlit`
- `pandas`
- `pandasai`

Note: `test.py` also imports `python-dotenv` (`from dotenv import load_dotenv`), so install it if needed:

```bash
pip install python-dotenv
```

## Setup

```bash
python -m venv .venv
```

### Windows (PowerShell)

```powershell
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
pip install python-dotenv
```

### macOS/Linux

```bash
source .venv/bin/activate
pip install -r requirements.txt
pip install python-dotenv
```

## Run

```bash
streamlit run test.py
```

Then open the local URL shown by Streamlit (usually `http://localhost:8501`).

## Usage

1. Upload `Table1` and `Table2` CSV files.
2. Optionally upload a template CSV.
3. Enter the column names you want in the output.
4. Click **Submit**.
5. Review the generated answer table and executed code section.

## Project Structure

- `test.py` - main Streamlit app (UI, preprocessing, PandasAI flow)
- `requirements.txt` - Python dependency list
- `pandasai.log` - runtime log output (generated)

## Security Notes

- Keep API keys and secrets only in `.env`.
- Never commit `.env` to version control.
- Review generated code shown in the app before trusting outputs in production workflows.
