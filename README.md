# AI Competitor Intel

A small Python and Streamlit demo that extracts visible paragraph text from a public webpage and uses Google's Gemini API to draft a competitor-messaging summary.

> **Status:** Prototype/demo. This is not a production-grade crawler or a validated market-research system. Website extraction can fail on JavaScript-heavy sites, and AI-generated analysis can be inaccurate. Respect each site's terms, robots guidance, copyright, and rate limits before analyzing content.

## Live demo

[Open the Streamlit demo](https://bharath-intel-scraper.streamlit.app)

## Requirements

- Python 3.10 or newer (verify against your deployment environment)
- A Google AI Studio API key with access to a supported Gemini model
- Internet access to the target website and Gemini API

## Run locally

```bash
git clone https://github.com/Bharath200359/ai-competitor-intel.git
cd ai-competitor-intel
python -m venv .venv
```

Activate the environment:

- Windows PowerShell: `.\.venv\Scripts\Activate.ps1`
- macOS/Linux: `source .venv/bin/activate`

Install dependencies and launch the interface:

```bash
python -m pip install -r requirements.txt
streamlit run app.py
```

Enter your own Gemini API key in the app. Never commit API keys or put them in source code. API usage may incur costs depending on your provider account and current terms.

## CLI version

Run `python main.py` to use the terminal interface. It reads `GEMINI_API_KEY` from the environment, or prompts for a key interactively.

## Current limitations and release checklist

- The current scraper follows redirects and does not yet implement a complete SSRF defense; do not expose it as a public arbitrary-URL scraping service without network/IP validation and redirect checks.
- Extraction is limited to paragraph elements and a short text sample; JavaScript-rendered pages may return little or no content.
- Confirm the configured Gemini model is available to your account before deployment; provider model availability changes over time.
- Add automated tests, URL/IP validation, graceful provider error handling, and a supported dependency update policy before calling this production-ready.
- The current dependencies are pinned for reproducibility, not guaranteed to be the latest secure versions. Review them before every release.

## License

No project-specific license file is currently present. Until a license is added, do not assume this repository grants permission to redistribute or sell the code. Verify ownership and choose a license before commercial distribution.
