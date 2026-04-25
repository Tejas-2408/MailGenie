# MailGenie 🧞‍♂️

**MailGenie** is an intelligent AI-powered email assistant designed to eliminate the friction of professional communication. By leveraging Large Language Models, it helps users generate contextually relevant, tone-appropriate, and concise email responses in seconds.

Live Demo: [https://mailgenie-ikfh.onrender.com](https://mailgenie-ikfh.onrender.com)

---

## ✨ Why "MailGenie"?
The name **MailGenie** stems from the idea of having a powerful, wish-granting assistant for your inbox. Just as a genie simplifies complex tasks with a flick of a wrist, MailGenie takes the "wish" or "intent" of the user (e.g., "reply politely to this meeting request") and instantly manifests a fully drafted, professional email. It aims to grant users the most valuable resource: **Time**.

---

## 🛠 Tech Stack

### Frontend
- **React.js**: For a dynamic and responsive user interface.
- **Vite**: Ultra-fast frontend build tool.
- **Tailwind CSS**: For modern, utility-first styling.
- **Axios**: For handling asynchronous API requests.

### Backend (REST API)
- **Java & Spring Boot**: Robust framework for building the production-grade REST API.
- **Spring Web**: To handle HTTP requests and CORS configurations.
- **Gemini AI API**: Integration with Google's generative AI models for intelligent text synthesis.
- **Maven**: Dependency management and build automation.

### Infrastructure & Deployment
- **Render**: Used for hosting both the frontend and backend as independent, connected services.
- **Docker**: Containerization used to ensure consistent backend deployment.

---

## 🚀 Deployment on Render

This project follows a **Decoupled Architecture**, where the Frontend and Backend are deployed as separate entities on Render and communicate via a RESTful interface.

### 1. Backend (email-writer-sb)
- **Environment**: Docker
- **Build Command**: Render automatically detects the `Dockerfile` in the root.
- **Key Configuration**: 
  - Ensure `GOOGLE_API_KEY` is added to the Environment Variables.
  - Port is dynamically bound using `server.port=${PORT:8080}`.
  - CORS is configured to allow requests from the specific Frontend URL.

### 2. Frontend (email-writer-react)
- **Environment**: Static Site
- **Build Command**: `npm install && npm run build`
- **Publish Directory**: `dist`
- **Connection**: The frontend is configured to point its Axios base URL to the Backend Render URL.

---

## 🧩 Chrome Extension
In addition to the web platform, MailGenie includes a **Chrome Extension** (found in the `mail-genie-extension` directory) for a seamless experience directly within your browser.

### How to Load Locally:
1. Open Chrome and navigate to `chrome://extensions/`.
2. Enable **Developer mode** (toggle in the top right).
3. Click **Load unpacked**.
4. Select the `mail-genie-extension` folder from this repository.
5. The MailGenie icon will now appear in your browser, ready to assist you on any webpage.

---

## 🔧 Installation & Local Setup

1. **Clone the repo:**
   ```bash
   git clone [https://github.com/Tejas-2408/MailGenie.git](https://github.com/Tejas-2408/MailGenie.git)
   ```

2. **Run Backend:**
   - Navigate to `email-writer-sb`.
   - Add your API key in `application.properties`.
   - Run `./mvnw spring-boot:run`.

3. **Run Frontend:**
   - Navigate to `email-writer-react`.
   - Run `npm install` then `npm run dev`.

---

*Developed by [Tejas](https://github.com/Tejas-2408)*
```