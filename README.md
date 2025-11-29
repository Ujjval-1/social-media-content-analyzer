🚀 Social Media Content Analyzer

A production-ready full-stack application that extracts text from PDFs and images, analyzes it, and generates AI-powered suggestions to boost social media engagement.
👉 Live Demo: https://social-media-content-analyzer-gamma.vercel.app/

✨ Features
📤 Seamless File Upload

Drag-and-drop or manual selection

Accepts: PDF, PNG, JPG, JPEG

Clean UI with toast-based notifications

🔍 Accurate Local Text Extraction

PDFs: processed via pdf-parse

Images: processed using local Tesseract OCR

100% cloud-free OCR for faster and more secure processing

Fully compatible with deployment platforms

🤖 AI-Based Engagement Enhancements

Powered by Gemini Flash:

Readability corrections

Tone enhancement

Hashtag generation

CTA improvements

Virality/engagement boost suggestions

⚙️ Background Job Queue System

Built on Bull Queue + Redis

Heavy tasks (OCR + AI) run in background workers

Main API remains fast, stable, and non-blocking

🔁 Real-Time Status Updates

Frontend polls backend job status

Extracted text appears first

Suggestions arrive after processing

Smooth, responsive user experience

🏗️ System Architecture
React → Node API → Bull Queue → Worker → Tesseract OCR + Gemini AI
           ↑                                ↓
      Polling ←────────────── Store & return results

⚡ Tech Stack
Frontend

React + Vite

Axios

React Hot Toast

Backend

Node.js + Express

Bull Queue

Redis

pdf-parse

Tesseract OCR (local)

Gemini Flash Model

🚀 Setup Instructions (Local Development)
1️⃣ Install dependencies
cd server && npm install
cd client && npm install

2️⃣ Start Redis
redis-server

3️⃣ Create server .env
PORT=4000
GEMINI_API_KEY=your_api_key_here
REDIS_URL=redis://127.0.0.1:6379

4️⃣ Start the backend
npm run dev

5️⃣ Start the frontend
npm run dev

📝 Summary (Under 200 Words)

This project extracts text from PDFs and images to help users optimize their social media posts using AI-powered suggestions. PDF text is extracted using pdf-parse, while images are processed through local Tesseract OCR—ensuring no cloud OCR dependency. Heavy, time-consuming operations like OCR and AI generation are executed inside Bull Queue workers connected via Redis, allowing the main API to stay responsive. The frontend continuously polls for job updates, showing extracted text first and AI suggestions afterward. Temporary files created during extraction are deleted immediately after processing, making the system clean, scalable, and deployment-friendly. The app is suitable for production use and handles large workloads efficiently.