# studyforge
AI study companion that turns notes, PDFs, slides, and voice recordings into summaries, flashcards, quizzes, revision plans, and guided doubt solving for students.

# StudyForge

## 🚀 Overview

StudyForge is an AI study companion for students that transforms learning materials into practical study aids. Users can upload notes, PDFs, slides, or voice recordings and get summaries, flashcards, quizzes, revision plans, and guided answers to doubts.

It is designed for students who want to save time, revise more effectively, and turn scattered material into structured study sessions.

## ✨ Features

- Upload notes, PDFs, slides, and voice recordings
- Generate concise study summaries
- Create flashcards from uploaded content
- Build practice quizzes from study material
- Produce revision plans for upcoming exams
- Ask questions about the uploaded content and get guided answers
- Organize study sessions by subject or topic

## 🧠 Problem It Solves

Students often have too much raw material and too little time. Notes are incomplete, PDFs are long, slides are dense, and voice recordings are hard to revisit. StudyForge reduces the effort required to review material by converting them into formats that are easier to learn from and revise.

## 💡 Solution

StudyForge combines document ingestion, content extraction, and AI-assisted learning workflows into one app. Instead of manually summarizing notes or creating flashcards, students can upload their material and instantly get structured study outputs that are ready for revision and self-testing.

The product is focused on practical learning outcomes:

- understand faster with summaries
- remember better with flashcards
- test knowledge with quizzes
- stay organized with revision plans
- clear doubts using the source material itself

## 🏗️ Architecture (High-Level)

### System components

- **Web app**: uploads files, displays generated study assets, and handles user interaction
- **API backend**: manages authentication, file metadata, study content generation, and user requests
- **Processing worker**: extracts text from PDFs, slides, and audio transcripts
- **AI layer**: generates summaries, flashcards, quizzes, plans, and answers
- **Storage**: stores original files, extracted text, and generated study artifacts
- **Database**: stores users, uploads, content chunks, and generated outputs

### Data flow

1. A student uploads a file or recording.
2. The backend stores the file and creates a processing job.
3. The worker extracts text or transcript content.
4. The AI layer converts that content into study outputs.
5. Results are saved and shown in the dashboard.
6. The student can revisit, search, and continue studying from the generated material.

## 📦 Tech Stack

- **Frontend**: Next.js, TypeScript, Tailwind CSS, shadcn/ui
- **Backend**: FastAPI or NestJS
- **AI / NLP**: LLM API, embeddings, retrieval pipeline
- **Database**: PostgreSQL, pgvector
- **Queue / Cache**: Redis
- **Storage**: S3-compatible object storage
- **Deployment**: Docker, GitHub Actions, Vercel, Render/Fly.io/Railway

## ⚙️ Installation

### Prerequisites

- Node.js 20+
- Python 3.11+ if using FastAPI workers
- PostgreSQL 15+
- Redis
- An API key for your LLM provider
- S3-compatible storage credentials

### Setup

1. Clone the repository:

```bash
git clone https://github.com/your-org-name/studyforge.git
cd studyforge
```

2. Install frontend dependencies:

```bash
npm install
```

3. Set up environment variables:

```bash
cp .env.example .env.local
```

4. Configure the required values:

```bash
NEXT_PUBLIC_APP_URL=http://localhost:3000
DATABASE_URL=postgresql://user:password@localhost:5432/studyforge
REDIS_URL=redis://localhost:6379
LLM_API_KEY=your_api_key
STORAGE_BUCKET=studyforge-files
STORAGE_REGION=your-region
```

5. Run database migrations:

```bash
npm run db:migrate
```

6. Start the development server:

```bash
npm run dev
```
7. Start the worker process in a separate terminal:

```bash
npm run worker
```

## ▶️ Usage

1. Sign in or create an account.
2. Upload a PDF, slide deck, note file, or voice recording.
3. Choose the output you need:
-summary
-flashcards
-quiz
-revision plan
-doubt solving
4. Review the generated study material in the dashboard.
5. Save, revisit, or regenerate outputs as needed.

## 📁 Project Structure

studyforge/
├── app/                  # Next.js application routes and pages
├── components/          # Reusable UI components
├── lib/                 # Shared utilities and helpers
├── services/             # API clients and business logic
├── workers/              # Background jobs for file processing and AI tasks
├── prisma/ or db/        # Database schema and migrations
├── public/               # Static assets
├── tests/                # Unit and integration tests
├── docs/                 # Product and technical documentation
├── .env.example          # Environment variable template
└── README.md             # Project overview and setup guide

## 🔐 Permissions / Security Notes

- Files should be private by default and accessible only to the owning user.
- Transcripts and generated content may contain sensitive academic material, so access control must be enforced on every request.
- Store API keys only in server-side environment variables.
- Add file type validation and size limits to reduce abuse.
- Sanitize extracted text before passing it into downstream systems.
- Use signed URLs or controlled download endpoints for uploaded files.

## 🛣️ Roadmap (V1 focused)

- Support upload and extraction for PDFs, notes, slides, and voice recordings
- Add summary generation with selectable length
- Generate flashcards and quizzes from uploaded content
- Add revision plan creation based on exam date or study deadline
- Add content search across uploaded material
- Add basic doubt solving with source-grounded answers
- Add subject folders and study session history

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make your changes with clear tests where possible.
4. Run formatting and test checks locally.
5. Open a pull request with a concise description of the change.

Please keep contributions aligned with the project’s V1 scope: practical study tooling, clean UX, and reliable content processing.

## 📄 License

This project is licensed under the **Apache 2.0 License**.  
See the `LICENSE` file for details.

---

## 🔖 Optional Enhancements

**Suggested GitHub topics (tags):**

- `education`
- `edtech`
- `ai`
- `students`
- `study-tools`
- `flashcards`
- `quiz-generator`
- `note-taking`
- `pdf-processing`
- `rag`
- `nextjs`
- `fastapi`

## 📚 Documentation

- [Documentation Hub](./docs/README.md)
- [PRD](./docs/prd/prd-v1.md)
- [TRD](./docs/trd/trd-v1.md)
- [Presentation Deck](./docs/presentations/studyforge-overview.pptx)
  
