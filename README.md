# Real-Time Chat Application 💬

A robust, real-time messaging platform built with **Spring Boot** and **WebSockets**. This application allows multiple users to connect to a common chat room and exchange messages instantly with a seamless, responsive UI.

Live Demo: [https://chatapp-l3rw.onrender.com](https://chatapp-l3rw.onrender.com)

---

## 🚀 Features

- **Real-Time Communication**: Leveraging STOMP over WebSockets for instant message delivery.
- **Dynamic UI**: Simple and intuitive interface for joining chat rooms and messaging.
- **User Presence**: Broadcasts when a user joins or leaves the chat.
- **Dockerized**: Fully containerized for easy deployment and consistent environments.
- **Cloud Hosted**: Deployed on Render with automated CI/CD via GitHub.

---

## 🛠 Tech Stack

- **Backend**: Java, Spring Boot, Spring WebSocket.
- **Frontend**: HTML5, CSS3, JavaScript (SockJS, STOMP.js).
- **Build Tool**: Maven.
- **Deployment**: Docker, Render.

---

## 🏗 Project Structure

- `src/main/java/com/chat/config`: Contains WebSocket configuration (STOMP endpoints and message brokers).
- `src/main/java/com/chat/model`: Defines the Message payload and type (CHAT, JOIN, LEAVE).
- `src/main/java/com/chat/controller`: Handles message routing and user session events.
- `src/main/resources/static`: Contains the frontend assets (index.html, css, and js).

---

## 📦 Deployment on Render

This application is deployed as a **Dockerized Web Service** on Render.

### Deployment Configuration:
1. **Runtime**: Docker
2. **Port Binding**: The app is configured to listen on the port provided by Render using `server.port=${PORT:8080}`.
3. **Memory Management**: Optimized with JVM flags (`-Xmx300m`) to run efficiently on Render's free tier.
4. **Environment**: The `Dockerfile` handles the multi-stage build (Maven build followed by JRE runtime).

---

## 🔧 Local Setup & Installation

Follow these steps to run the project locally:

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Tejas-2408/ChatApp.git](https://github.com/Tejas-2408/ChatApp.git)
   cd ChatApp
   ```

2. **Build the project:**
   ```bash
   mvn clean install
   ```

3. **Run the application:**
   ```bash
   mvn spring-boot:run
   ```

4. **Access the App**:
   Open your browser and navigate to `http://localhost:8080`.

---

## 💡 Important Notes for Render Free Tier

- **Cold Starts**: Since the app is hosted on the free tier, it may take 30-50 seconds to "wake up" after a period of inactivity.
- **WebSocket Stability**: Render supports WebSockets natively; however, ensure your frontend includes reconnection logic to handle occasional timeouts on the free instance.

---

*Developed by [Tejas](https://github.com/Tejas-2408)*
```