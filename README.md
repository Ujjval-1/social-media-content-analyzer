🚀 Social Media Content Analyzer

A comprehensive full-stack tool that helps users extract text from PDFs and images, analyze it, and receive AI-driven recommendations to improve social media engagement.

✨ Key Features
📤 File Upload

Drag-and-drop or select files manually

Supports: PDF, PNG, JPG, JPEG

Real-time notifications using toast messages

🔍 Text Extraction

PDFs processed locally via pdf-parse

Images processed locally using Tesseract OCR

No cloud dependency → faster, secure, and deployment-ready

🤖 AI Engagement Suggestions

Powered by Gemini Flash

Improves readability, tone, hashtags, call-to-actions, and virality

Suggestions appear after text extraction

⚙️ Backend Processing

Built with Bull Queue + Redis for asynchronous tasks

Non-blocking workflow for OCR and AI operations

Scalable worker system for heavy processing

🔁 Real-Time Updates

Frontend polls job status

Text results appear first, followed by AI suggestions

Smooth and responsive UI

🏗️ Architecture
React → Node API → Bull Queue → Worker → Tesseract OCR + Gemini AI
           ↑                               ↓
      Polling ←────────── Save result JSON

⚡ Tech Stack

Frontend: React + Vite, Axios, React Hot Toast
Backend: Node.js, Express, Bull Queue, Redis, pdf-parse, Tesseract OCR (local), Gemini Flash API

🚀 Setup Instructions

Install dependencies:

cd server && npm install
cd client && npm install


Start Redis:

redis-server


Create .env in the server folder:

PORT=4000
GEMINI_API_KEY=your_api_key_here
REDIS_URL=redis://127.0.0.1:6379


Start backend:

npm run dev


Start frontend:

npm run dev

📝 Project Summary

This tool streamlines text extraction from PDFs and images to optimize social media content. All processing happens locally or in background workers (via Bull Queue + Redis), keeping the API fast and responsive. The system handles heavy OCR and AI workloads asynchronously, ensures temporary files are removed post-processing, and provides real-time updates to the frontend. Fully self-contained and deployment-friendly, it’s ready for production-level tasks.