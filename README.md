# 📝 Notra — AI-Powered Note Taking App

> A full-stack, real-time, AI-enhanced note-taking application built with React, Node.js, MongoDB, and Google Gemini AI.

---

## ✨ Features

- 🤖 **AI Assistant** — Chat with Gemini AI directly within your notes
- ✍️ **Smart Editor** — Block-based editor with slash (`/`) command menu
- 📋 **AI Actions** — Summarize, explain, generate study questions, fix grammar, translate & more
- 🎤 **Voice Recording** — Record audio and transcribe notes
- 🖼️ **OCR Support** — Extract text from images via Tesseract.js
- 🗂️ **Workspaces** — Organize notes into collaborative workspaces
- 🔄 **Real-time Collaboration** — Live editing powered by Socket.IO
- 🔐 **Auth** — JWT-based authentication with bcrypt password hashing
- 📱 **Responsive UI** — Built with Tailwind CSS v4 and Framer Motion animations
- 🌙 **Demo Mode** — Works without an API key using smart fallback responses

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 19, Vite, Tailwind CSS v4, Zustand, Framer Motion |
| **Backend** | Node.js, Express.js, Socket.IO |
| **Database** | MongoDB (Mongoose) |
| **AI** | Google Gemini 2.0 Flash (`@google/generative-ai`) |
| **OCR** | Tesseract.js |
| **Auth** | JSON Web Tokens (JWT), bcryptjs |
| **File Upload** | Multer |
| **Logging** | Winston |

---

## 📁 Project Structure

```
notra/
├── client/                  # React frontend (Vite)
│   └── src/
│       ├── components/
│       │   ├── ai/          # AI chat panel, voice recorder
│       │   ├── editor/      # Block editor, slash commands
│       │   ├── layout/      # Navbar, sidebar, panels
│       │   └── ui/          # Reusable UI components
│       ├── hooks/           # Custom React hooks
│       ├── pages/           # Landing, Login, Dashboard, Workspace
│       ├── services/        # API service layer
│       ├── stores/          # Zustand global state stores
│       └── utils/           # Constants and helpers
├── server/                  # Express backend
│   ├── config/              # Database connection
│   ├── controllers/         # Route controllers (auth, notes, workspaces, AI)
│   ├── middleware/          # Auth, error handling, file upload
│   ├── models/              # Mongoose models (User, Note, Workspace, ChatHistory)
│   ├── routes/              # API route definitions
│   ├── services/            # Business logic (AI, OCR, voice, embeddings)
│   ├── sockets/             # Socket.IO collaboration handler
│   └── utils/               # Logger
├── shared/                  # Shared constants between client and server
├── package.json             # Root scripts (runs both client & server)
└── .env                     # Environment variables (not committed)
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** v18+
- **MongoDB** (local or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))
- **Google Gemini API Key** — [Get one free](https://aistudio.google.com/app/apikey)

### 1. Clone the repository

```bash
git clone https://github.com/your-username/notra.git
cd notra
```

### 2. Set up environment variables

Create a `.env` file in the **root directory** (and/or inside `server/`):

```env
# MongoDB connection string
MONGODB_URL=mongodb+srv://<user>:<password>@cluster.mongodb.net/notra

# JWT secret (use a long random string in production)
JWT_SECRET=your_super_secret_jwt_key

# Google Gemini API Key
GEMINI_API_KEY=your_gemini_api_key_here

# Server settings
PORT=5000
NODE_ENV=development

# Client URL (for CORS)
CLIENT_URL=http://localhost:5173
```

> **Note:** The app runs in **demo mode** with pre-built AI responses if `GEMINI_API_KEY` is not provided. All other features still work.

### 3. Install dependencies

```bash
npm run install-all
```

This installs dependencies for the root, `server/`, and `client/` packages.

### 4. Run the development server

```bash
npm run dev
```

This concurrently starts:
- 🖥️ **Frontend** at `http://localhost:5173`
- ⚙️ **Backend** at `http://localhost:5000`

---

## 📜 Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start both client and server in development mode |
| `npm run server` | Start only the backend server |
| `npm run client` | Start only the frontend (Vite) |
| `npm run install-all` | Install all dependencies (root + server + client) |

Inside `client/`:

| Command | Description |
|---|---|
| `npm run build` | Build the frontend for production |
| `npm run preview` | Preview the production build |
| `npm run lint` | Run ESLint |

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Register a new user |
| `POST` | `/api/auth/login` | Login and receive JWT |
| `GET` | `/api/notes` | Fetch all notes |
| `POST` | `/api/notes` | Create a new note |
| `PUT` | `/api/notes/:id` | Update a note |
| `DELETE` | `/api/notes/:id` | Delete a note |
| `GET` | `/api/workspaces` | Fetch all workspaces |
| `POST` | `/api/workspaces` | Create a workspace |
| `POST` | `/api/ai/chat` | Send a message to Gemini AI |
| `POST` | `/api/ai/action` | Perform an AI text action |
| `GET` | `/api/health` | Health check |

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License**.

---

<p align="center">Built with ❤️ using React, Node.js & Google Gemini AI</p>
