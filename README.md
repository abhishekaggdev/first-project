# Ask your PDF

A small Streamlit app that extracts text from a PDF, finds relevant passages, and
answers questions about those passages with page citations using the Gemini API.

## Run locally

Requires Python 3.10 or later and a Gemini API key. Create a key in
[Google AI Studio](https://aistudio.google.com/apikey).

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
$env:GEMINI_API_KEY = "your-api-key"
streamlit run app.py
```

Alternatively, leave `GEMINI_API_KEY` unset and enter the key in the app. The app
does not save the key to a file. Uploaded PDFs are processed in memory by the app;
the relevant text passages and conversation are kept in the Streamlit session.

The upload limit is 25 MB. Scanned PDFs without selectable text need to be OCR'd
before upload. Answers use Gemini 2.5 Flash and are limited to information found
in the retrieved PDF passages. Check Google's current [Gemini API pricing and
limits](https://ai.google.dev/gemini-api/docs/pricing); free-tier availability
and limits depend on Google's current terms.
