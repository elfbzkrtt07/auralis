# Auralis — AI-Powered Product Recognition App

Auralis is a **cross-platform mobile application** that extracts and organizes product information mentioned by influencers across platforms like Instagram, TikTok, and YouTube.  
When a user shares a video link, Auralis automatically detects the products, their descriptions, and pricing information using **AI** — allowing users to save, edit, and organize items into custom lists.

---

## Features

- **Smart Product Extraction:** Uses **OpenAI GPT-4o** to analyze social media video captions and comments.
- **Automatic Structuring:** AI returns clean JSON with product name, purpose, category, and price estimates.
- **Personal Lists:** Create, edit, and manage multiple lists for different product categories.
- **Cross-List Management:** Move items between lists or mark them as purchased.
- **Cloud Sync:** Backed by AWS for persistent data storage and scalability.
- **Modern UI:** Minimal lavender-pink themed interface designed in Figma.

---

## Tech Stack

| Layer | Technology | Description |
|-------|-------------|-------------|
| **Frontend (Mobile)** | [React Native (TypeScript, Expo)](https://reactnative.dev/) | Cross-platform UI for iOS & Android |
| **Backend (API)** | [FastAPI](https://fastapi.tiangolo.com/) | High-performance Python backend |
| **AI Layer** | [OpenAI GPT-4o](https://platform.openai.com/docs) | Semantic extraction of product mentions |
| **Cloud** | [AWS Lambda](https://aws.amazon.com/lambda/), [API Gateway](https://aws.amazon.com/api-gateway/), [DynamoDB](https://aws.amazon.com/dynamodb/), [Cognito](https://aws.amazon.com/cognito/) | Serverless backend, authentication, and NoSQL storage |
| **DevOps** | [Docker](https://www.docker.com/), [GitHub Actions](https://github.com/features/actions) | Containerization and CI/CD automation |
| **Design** | [Figma](https://figma.com/) | UI mockups and color palette (lavender-pink theme) |

---

## Project Structure
## Project Structure

```
Auralis/
│
├── frontend/ # React Native (Expo) app
│   ├── src/
│   │   ├── components/ # UI components
│   │   ├── screens/ # Navigation screens
│   │   ├── services/ # API calls
│   │   └── utils/ # Helpers and constants
│   └── package.json
│
├── backend/ # FastAPI backend
│   ├── app/
│   │   ├── main.py # Entrypoint
│   │   ├── routes/ # API endpoints
│   │   ├── models/ # Data models / schemas
│   │   ├── services/ # GPT-4o, AWS integrations
│   │   └── utils/
│   └── requirements.txt
│
├── infrastructure/ # Deployment scripts, CI/CD
│   ├── Dockerfile
│   ├── lambda_handler.py
│   └── github-actions.yml
│
└── README.md
```

---
## Setup Guide

### 1) Clone the Repository
git clone https://github.com/elfbzkrtt07/auralis
cd auralis

### 2) Backend (FastAPI)
cd backend
pip install -r requirements.txt
uvicorn app.main:app --reload

### 3) Frontend (React Native)
cd frontend
npm install
npx expo start

---

## Deployment

Auralis uses a serverless architecture with AWS Lambda, API Gateway, DynamoDB, Cognito, and Dockerized FastAPI.

### Docker Commands
docker build -t auralis-backend .
docker run -p 8000:8000 auralis-backend

### Deployment Flow
1. Build Docker image  
2. Push to Amazon ECR  
3. Deploy to AWS Lambda  
4. Expose via API Gateway  
5. Add environment variables in Lambda  
6. GitHub Actions automates CI/CD



