## Medi-Audit (AI Health Assistant)

### Core Objective
A medical report analyzer that uses RAG to help users understand lab results. Focus: Data privacy, accuracy, and clear UX.

### Tech Stack (Strict Adherence)
* **Frontend:** Next.js 16+ (App Router), TypeScript, Tailwind CSS, Lucide React (Icons), shadcn.
* **Backend:** Node.js ( Next.js API Routes),  Nextjs Server component, Server Actions
* **Authentication**: Clerk(Identity & Session Management).
* **Database:** PostgreSQL with `pgvector` extension for vector similarity search.
* **AI:** Gemini Pro (LLM), Gemini Text Embeddings, LangChain.js.
* **Storage:** AWS S3 (via SDK v3) for PDF/Image storage.
* **Package Manager:** pnpm.

### Key Feature Workflows
1.  **Ingestion:** User uploads PDF/Image $\rightarrow$ Save to S3 $\rightarrow$ Extract text via Gemini Vision/OCR.
2.  **RAG Pipeline:** Chunk text $\rightarrow$ Generate embeddings $\rightarrow$ Upsert to `pgvector`.
3.  **Chat Interface:** Semantic search in Postgres $\rightarrow$ Feed relevant chunks to Gemini $\rightarrow$ Generate patient-friendly response.
4.  **Trend Analysis:** Compare current biomarkers against historical SQL data for the same user.
5.  **Upload History:** User views past PDF/Image uploads $\rightarrow$ See file type, upload timestamp, and AI-generated summary for each report.

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.
