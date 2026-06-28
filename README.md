# 📚 Novel World

> **Upload a PDF and watch it come alive. Every character has a face, a voice, and a story.**

**Novel World** is an AI-powered multimedia platform that transforms written novels into immersive interactive experiences, visual storyboards, audio dramas, and full MP4 cinematic movies. By parsing novel PDFs and leveraging LLM analysis, visual generation, and voice synthesis, Novel World extracts rich narrative structures, brings characters to life, and synthesizes cinematic scenes.

---

## 🚀 Key Features

* 📄 **PDF Upload & Text Parsing:** Upload any novel in PDF format. Automatic extraction of text, chapters, and metadata.
* 🎭 **Dramatis Personae (Character Analysis):** AI-driven identification of protagonists, antagonists, supporting cast, and minor characters with auto-generated visual avatars and voice profiles.
* 📈 **Story Arc & Interactive Timeline:** Visual emotional intensity charting (Mysterious, Tense, Sad, Violent) with filtered event timelines.
* 🎙️ **Script & Voice Generation:** Line-by-line dialogue breakdown with interactive audio playback for each character.
* 🎬 **Cinema Mode:** Dynamic scene player with synchronized audio, dialogue captions, and visual imagery.
* 📋 **Visual Storyboard & PDF Export:** Full multi-scene storyboard grid ready for export.
* 🎥 **Movie Composer:** Automated production pipeline utilizing FFmpeg to render generated images and character audio into a downloadable MP4 film.

---

## 📸 Screenshots Showcase

### 1. Library & Dashboard
| Landing & Library View | Novel Dashboard |
| :---: | :---: |
| ![Library View](screenshots/Screenshot%202026-06-28%20121019.png) | ![Novel Dashboard](screenshots/Screenshot%202026-06-28%20121100.png) |
| *Upload novels via drag-and-drop and manage your personal library.* | *View high-level overview, synopsis, word counts, and key metrics.* |

---

### 2. Character Extraction & Cast Overview
| Dramatis Personae |
| :---: |
| ![Characters](screenshots/Screenshot%202026-06-28%20121119.png) |
| *AI automatically categorizes characters by role (Protagonist, Antagonist, Supporting, Minor).* |

---

### 3. Story Arc & Narrative Timeline
| Narrative Event Timeline | Interactive Event Details |
| :---: | :---: |
| ![Story Timeline](screenshots/Screenshot%202026-06-28%20121153.png) | ![Event Arc](screenshots/Screenshot%202026-06-28%20121210.png) |
| *Track emotional arcs across chapters and filter events by mood.* | *Inspect scene details and trigger AI scene generation directly.* |

---

### 4. Dialogue, Voices & World Building
| Script & Interactive Voice Playback | World Map & Locations |
| :---: | :---: |
| ![Script & Voices](screenshots/Screenshot%202026-06-28%20121228.png) | ![World Map](screenshots/Screenshot%202026-06-28%20121244.png) |
| *Listen to synthesized character dialogue lines in real time.* | *Explore mapped story environments and key locations.* |

---

### 5. Cinema Experience & Production Pipeline
| Cinema Mode Player | Visual Storyboard Export |
| :---: | :---: |
| ![Cinema Mode](screenshots/Screenshot%202026-06-28%20121338.png) | ![Storyboard](screenshots/Screenshot%202026-06-28%20121406.png) |
| *Watch scenes unfold with dynamic audio and visual playback.* | *Export multi-scene storyboards as printable PDF files.* |

#### 🎞️ Movie Composer Pipeline
![Movie Composer](screenshots/Screenshot%202026-06-28%20121422.png)
*Automated 5-step production pipeline: PDF Extraction ➔ LLM Story Analysis ➔ Image Generation ➔ Voice Synthesis ➔ FFmpeg MP4 Export.*

---

## 🛠️ Tech Stack & Architecture

Novel World is built as a high-performance TypeScript monorepo powered by `pnpm`.

### **Frontend App (`artifacts/novel-world`)**
* **Framework:** React 18 with Vite
* **Routing:** Wouter
* **Styling & UI:** Tailwind CSS, Radix UI primitives, Lucide Icons, Framer Motion
* **State Management & Data Fetching:** TanStack React Query with auto-generated API client hooks (`@workspace/api-client-react`)

### **Backend API Server (`artifacts/api-server`)**
* **Framework:** Express 5 (Node.js)
* **AI Integration:** OpenAI API for structured story analysis, image generation, and speech synthesis
* **File Processing:** `pdf-parse` for text extraction, Multer for upload management, and FFmpeg for video rendering
* **Logger:** Pino & Pino HTTP logging

### **Database & Shared Libraries (`lib/`)**
* **Database & ORM:** PostgreSQL managed via Drizzle ORM (`@workspace/db`)
* **Validation & Schemas:** Zod (`@workspace/api-zod`) and OpenAPI specifications (`@workspace/api-spec`)

---

## ⚙️ Getting Started

### Prerequisites
* **Node.js**: >= 20.x
* **Package Manager**: `pnpm` (install via `npm i -g pnpm`)
* **Database**: PostgreSQL database instance

### Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd Novel-world-1
   ```

2. **Install dependencies:**
   ```bash
   pnpm install
   ```

3. **Configure Environment Variables:**
   Create `.env` files in `artifacts/api-server` and `artifacts/novel-world` with required keys:
   ```env
   DATABASE_URL=postgresql://user:password@localhost:5432/novel_world
   OPENAI_API_KEY=your_openai_api_key
   ```

4. **Run Development Mode:**
   ```bash
   pnpm run dev
   ```
   * The API server and frontend app will launch concurrently in development mode.

---

## 📜 License
This project is licensed under the MIT License.
