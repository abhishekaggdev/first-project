# Ask your PDF

A small Streamlit app that extracts text from a PDF, finds relevant passages, and
answers questions about those passages with page citations using OpenAI.

## Run locally

Requires Python 3.10 or later and an OpenAI API key.

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
$env:OPENAI_API_KEY = "your-api-key"
streamlit run app.py
```

Alternatively, leave `OPENAI_API_KEY` unset and enter the key in the app. The app
does not save the key to a file. Uploaded PDFs are processed in memory by the app;
the relevant text passages and conversation are kept in the Streamlit session.

The upload limit is 25 MB. Scanned PDFs without selectable text need to be OCR'd
before upload. Answers use `gpt-4o-mini` and are limited to information found in
the retrieved PDF passages.
