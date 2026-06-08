# Author

Designed and developed by **Bao H. Nguyen**.

- LinkedIn: [Bao Hong Gia Nguyen](https://www.linkedin.com/in/bao-hong-gia-nguyen/)

---

## AI Chat Hub

A unified chat interface for interacting with multiple AI providers: OpenAI GPT-5.1, Google Gemini 3 Pro, Perplexity Sonar Pro, and an intelligent Multi-LLM mode that auto-routes prompts to the best model.

---

## Features

- **Multi-Provider Chat**: Switch between OpenAI, Gemini, Perplexity, and Multi-LLM tabs
- **OpenAI GPT-5.1**: Logical reasoning, scenario analysis, and content creation
- **Google Gemini 3 Pro**: Document/multimodal analysis and AI image generation (Imagen 4)
- **Perplexity Sonar Pro**: Real-time web search with source citations
- **Multi-LLM Mode**: GPT classifies your prompt and auto-routes to the best provider
- **File Uploads**: Attach up to 10 files per message (PDF, images, spreadsheets, text, and more)
- **Authentication**: User registration and login with JWT; chat history cleared on logout
- **Prompt Log**: Browse your full paginated chat history across all providers
- **Summarize Note**: Paste notes and get concise, detailed, or bullet-point AI summaries
- **Mind Map Generator**: Convert notes or a topic into an interactive SVG mind map
- **Flash Card Generator**: Generate 5–20 flip-style study cards from any topic or notes
- **Markdown Rendering**: AI responses rendered with full GFM markdown support
- **Streaming Animation**: Typewriter-style effect for assistant responses
- **Responsive Design**: Works on desktop and mobile

---

## Technologies Used

- **Vite** — Fast build tool and development server
- **TypeScript** — Type-safe JavaScript
- **React 18** — UI framework
- **shadcn/ui** — Accessible component library built on Radix UI
- **Tailwind CSS** — Utility-first CSS framework
- **TanStack Query** — Server state management
- **react-markdown + remark-gfm** — Markdown rendering

---

## Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm, yarn, or bun
- A running backend API (default: `http://localhost:3000`)

### Installation

1. **Clone the repository:**
   ```sh
   git clone git@github.com:baong2911/AI-Chat-Hub.git
   cd ai-chat-hub
   ```

2. **Install dependencies:**
   ```sh
   npm install
   ```

3. **Configure environment:**

   Create a `.env` file in the root directory:
   ```env
   VITE_API_BASE_URL=http://localhost:3000
   ```

4. **Start the development server:**
   ```sh
   npm run dev
   ```

The application will be available at `http://localhost:5173`

---

## Backend API

The frontend expects a backend at `VITE_API_BASE_URL` with the following endpoints:

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and receive a JWT token |
| POST | `/api/chat` | Send a message to a provider |
| POST | `/api/chat/file` | Send a message with uploaded file IDs |
| POST | `/api/upload` | Upload a file and receive a permanent URL |
| POST | `/api/generate-image` | Generate an image via DALL-E 3 |
| GET | `/api/user-prompts` | Fetch paginated prompt history |

All authenticated endpoints require an `Authorization: Bearer <token>` header.

---

## Pages

| Route | Page | Description |
|-------|------|-------------|
| `/` | Chat | Main multi-provider chat interface |
| `/log` | Prompt Log | Paginated history of all your prompts |
| `/summarize` | Summarize Note | AI-powered note summarization |
| `/mindmap` | Mind Map | Visual hierarchical mind map from notes or a topic |
| `/flashcard` | Flash Cards | Interactive flip-card study deck |

---

## Usage

### OpenAI GPT-5.1
**Best for:** Logical reasoning, business analysis, and content creation

**Try prompts like:**
- "Analyze whether my business idea is logically viable and list the risks."
- "Predict how customer behavior will change if we increase pricing by 10%."
- "Explain the reasoning steps behind choosing Strategy A vs Strategy B for my startup."

---

### Gemini 3 Pro
**Best for:** Document/image analysis and AI image generation

**Ask mode — try prompts like:**
- "Analyze this business requirement document and identify missing details."
- "Compare these two business policy documents and list their differences."

**Generate Image mode — try prompts like:**
- "A futuristic city skyline at sunset with flying cars"
- "A cozy coffee shop interior with warm lighting and bookshelves"

---

### Perplexity Sonar Pro
**Best for:** Research with verified, cited sources

**Try prompts like:**
- "Find the latest market statistics for the U.S. e-commerce industry and cite sources."
- "Search for current regulations affecting cross-border shipping businesses."

---

### Multi-LLM Mode
**Best for:** When you're unsure which provider to use

GPT-5.1 first classifies your prompt into one of three categories, then routes it automatically:

| Category | Provider | Best for |
|----------|----------|----------|
| Content creation | GPT-5.1 | Writing, brainstorming, marketing copy |
| Current events | Gemini 3 Pro | News, trending topics, recent analysis |
| Academic / Fact research | Perplexity Sonar Pro | Science, history, sourced facts |

---

## File Upload Support

Files can be attached to any message (except Gemini image generation mode). Supported formats:

- **Documents:** `.txt`, `.md`, `.pdf`, `.json`, `.csv`, `.xls`, `.xlsx`
- **Images:** `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.bmp`, `.svg`

Maximum **10 files per message**. Files are uploaded immediately on selection and tracked with individual upload status indicators.

⭐ If you find this project useful, consider giving it a star.