# Legal Review Agent

**Legal Review Agent** is an AI-powered API that extracts key clauses and summarizes risks from legal PDF documents. Ideal for contract analysts, compliance officers, or legal teams.

## Features

- Extracts:
  - Obligations (e.g., "Party A shall...")
  - Penalties
  - Involved Parties
  - Important Dates
- Summarizes potential legal risks using a transformer-based model
- Accepts PDF uploads and returns a structured JSON response

## API Usage

### Endpoint
```
POST /analyze
Content-Type: multipart/form-data
```

### Request
Send a PDF file as `file` in `form-data`.

### Example (using cURL)
```bash
curl -X POST http://localhost:5000/analyze \
  -F 'file=@/path/to/contract.pdf'
```

### Response
```json
{
  "clauses": {
    "obligations": [...],
    "penalties": [...],
    "parties": [...],
    "dates": [...]
  },
  "risk_summary": [
    "This contract contains..."
  ]
}
```

## Deploy on Inferium

1. Push this repo to GitHub
2. Go to [https://inferium.io/space](https://inferium.io/space)
3. Choose "Upload Model"
4. Select GitHub Repository and paste the URL
5. Provide input: `multipart/form-data` with PDF as `file`
6. Output: JSON with clause and summary fields

---

Built with Python, Flask, and HuggingFace Transformers.
