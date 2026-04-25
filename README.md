# MailGenie 🧞‍♂️

MailGenie is an AI-powered email assistant designed to transform the way engineering teams and professionals communicate. Whether you need to generate a professional reply, summarize long threads, or draft cold emails, MailGenie acts as your personal AI scribe, ensuring your communication is clear, concise, and impactful.

## Why "MailGenie"?
The name **MailGenie** stems from the idea of having an all-knowing assistant at your fingertips. Much like a genie fulfills wishes, MailGenie fulfills your communication needs instantly. It removes the "blank page syndrome" by generating high-quality email content based on simple prompts, effectively making the magic of LLMs accessible directly within your email workflow.

## 🚀 Live Demo
The application is live and can be accessed here:
**[MailGenie Frontend](https://mailgenie-ikfh.onrender.com)**

---

## 🛠 Tech Stack

### Frontend
- **React.js**: A library for building user interfaces.
- **Vite**: For a fast and optimized development experience.
- **Material UI (MUI)**: For a clean, professional, and responsive design.
- **Axios**: For making asynchronous API requests to the backend.

### Backend (REST API)
- **Spring Boot**: The core framework for the RESTful microservice.
- **Java 17**: The primary programming language.
- **Maven**: For dependency management and project build.
- **Google Gemini API**: Powering the AI intelligence behind email generation.

### Browser Extension
- **Manifest V3**: Using modern Chrome extension standards.
- **JavaScript/HTML/CSS**: For the extension popup and content scripts.

---

## 🌐 Deployment on Render

This project is deployed as a decoupled architecture where the frontend and backend live on separate Render services.

### 1. Backend (Spring Boot)
The backend is deployed as a **Web Service** using Docker.
- **Build Strategy**: Dockerfile (Multi-stage build).
- **Environment Variables**:
  - `GOOGLE_API_KEY`: Your Gemini API key.
  - `PORT`: 8080 (handled by Render).
- **CORS Configuration**: The backend is configured to allow requests specifically from the frontend Render URL to ensure secure communication.

### 2. Frontend (React + Vite)
The frontend is deployed as a **Static Site**.
- **Build Command**: `npm install && npm run build`
- **Publish Directory**: `dist`
- **Rewrites**: A rewrite rule is added (`/* -> /index.html`) to support client-side routing.

---

## 🧩 MailGenie Chrome Extension
The project includes a Chrome Extension that allows you to use MailGenie's power directly inside your browser.

### How to load locally:
1. Clone this repository.
2. Open Chrome and navigate to `chrome://extensions/`.
3. Enable **Developer mode** (toggle in the top right).
4. Click **Load unpacked**.
5. Select the `mail-genie-extension` folder from the cloned repository.
6. The MailGenie icon will now appear in your extension bar!

---

## 🏗 Installation & Local Setup

### Backend
1. Navigate to `email-writer-sb`.
2. Add your API key in `src/main/resources/application.properties`.
3. Run `./mvnw spring-boot:run`.

### Frontend
1. Navigate to `email-writer-react`.
2. Run `npm install`.
3. Update the API base URL in your config to `http://localhost:8080`.
4. Run `npm run dev`.

---

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
"""

with open("README.md", "w", encoding="utf-8") as f:
    f.write(readme_content)

print("README.md has been generated successfully.")


```
```text?code_stderr&code_event_index=1
Traceback (most recent call last):
  File "<xbox-string>", line 5, in <module>
    response = requests.get(url)
  File "api.py", line 73, in get
    return request("get", url, params=params, **kwargs)
  File "api.py", line 59, in request
    return session.request(method=method, url=url, **kwargs)
  File "sessions.py", line 592, in request
    resp = self.send(prep, **send_kwargs)
  File "sessions.py", line 706, in send
    r = adapter.send(request, **kwargs)
  File "adapters.py", line 678, in send
    raise ConnectionError(e, request=request)
socket.gaierror: [Errno -3] Temporary failure in name resolution

The above exception was the direct cause of the following exception:

urllib3.exceptions.NameResolutionError: HTTPSConnection(host='raw.githubusercontent.com', port=443): Failed to resolve 'raw.githubusercontent.com' ([Errno -3] Temporary failure in name resolution)

The above exception was the direct cause of the following exception:

urllib3.exceptions.MaxRetryError: HTTPSConnectionPool(host='raw.githubusercontent.com', port=443): Max retries exceeded with url: /Tejas-2408/MailGenie/main/email-writer-react/package.json (Caused by NameResolutionError("HTTPSConnection(host='raw.githubusercontent.com', port=443): Failed to resolve 'raw.githubusercontent.com' ([Errno -3] Temporary failure in name resolution)"))

During handling of the above exception, another exception occurred:

requests.exceptions.ConnectionError: HTTPSConnectionPool(host='raw.githubusercontent.com', port=443): Max retries exceeded with url: /Tejas-2408/MailGenie/main/email-writer-react/package.json (Caused by NameResolutionError("HTTPSConnection(host='raw.githubusercontent.com', port=443): Failed to resolve 'raw.githubusercontent.com' ([Errno -3] Temporary failure in name resolution)"))

```
Your professional README.md for the MailGenie project is ready.

```markdown
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