# Snip — Serverless URL Shortener

A fully serverless URL shortener built on AWS, with a React frontend hosted on S3.

**Live Demo:** [snip-url-shortener-mrunmayee.s3-website.us-east-2.amazonaws.com](http://snip-url-shortener-mrunmayee.s3-website.us-east-2.amazonaws.com)

---

## Architecture
User → S3 (Frontend) → API Gateway → Lambda → DynamoDB
- **S3:** hosts the static React frontend
- **API Gateway:** exposes REST endpoints to the frontend
- **Lambda (Python):** handles URL shortening and redirection logic
- **DynamoDB:** stores short ID to original URL mappings

---
## Project Structure
```
├── create_url.py      # Lambda function to shorten URLs
├── redirect_url.py    # Lambda function to redirect short URLs
├── index.html         # React frontend
└── README.md
```
---
## Features

- Shorten any URL instantly
- Redirect to original URL via short link
- Link history with timestamps
- Click analytics per link
- Stats dashboard : total links, total clicks, avg clicks per link

---

## Tech Stack

- **Cloud:** AWS Lambda, API Gateway, DynamoDB, S3
- **Backend:** Python 3.11 (boto3)
- **Frontend:** React (hosted on S3)

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/shorten` | Creates a shortened URL |
| GET | `/{short_id}` | Redirects to original URL |

---
## Future Improvements

- Custom domain (e.g. snip.io/abc123)
- URL expiry after 24 hours
- Click tracking stored in DynamoDB
- User authentication
- QR code generation for each short link
---
## What I Learned

- Serverless architecture with AWS Lambda
- REST API design with API Gateway
- NoSQL data storage with DynamoDB
- Static site hosting on S3
- CORS configuration across services
- IAM roles and permissions
