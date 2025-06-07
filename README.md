**CodeWhiz** is a real-time collaborative code editor web application that allows multiple users to work on the same code file together. Whether you're working on a team project or simply pair programming, this app lets you create coding rooms, invite others, and collaborate seamlessly in your browser!

---

![ReactJS](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)![Codemirror](https://img.shields.io/badge/CodeMirror-D30707?style=for-the-badge&logo=CodeMirror&logoColor=white)![NodeJS](https://img.shields.io/badge/Node%20js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)![ExpressJS](https://img.shields.io/badge/Express%20js-000000?style=for-the-badge&logo=express&logoColor=white)![SocketIO](https://img.shields.io/badge/Socket.io-010101?&style=for-the-badge&logo=Socket.io&logoColor=white)![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

---

## ✨ Features

- **Real-Time Collaborative Editing**  
  - 🔄 See live code updates from other users instantly.
  - 👤 View the usernames of everyone connected to the session.
  - ✍️ See other users' cursors and actions as they edit in real time.

- **Create Public/Private Rooms**  
  - 🏠 Generate unique, shareable room URLs.
  - 🔒 Option to create private rooms for secure collaboration.

- **No Refresh Required**  
  - 🚫🔄 Experience real-time collaboration without needing to refresh your browser.

## 🛠 Built With

- **Frontend**  
  - ⚛️ React.js - For building a responsive, interactive user interface.
  - 🎨 CodeMirror (v5.65.2) - As the code editor UI component.

- **Backend**  
  - ⚙️ Node.js - For the server runtime.
  - 🌐 Express.js - As the server framework for managing requests.
  - 🧑‍💻 Socket.IO - Enables real-time, bidirectional communication between users.

- **Deployment**  
  - ⚡ Vercel - For easy and fast deployment.

- **Other Tools**  
  - 🔑 uuid - For generating unique room IDs.
  - 🍞 react-hot-toast - For providing sleek pop-up notifications (toasts).

## 📸 Demo

### **Home Page**  
Here's the app's home page where you can create and join rooms:

![Home Page](https://github.com/Aashay30/CodeWhiz/blob/main/screenshots/Home%20Page.png)

### **Room Creation**  
Easily generate a unique Room ID:

![Room ID](https://github.com/Aashay30/CodeWhiz/blob/main/screenshots/Room%20ID.png)

### **Editor Window**  
This is the main editor window, with a dashboard showing all connected users and the shared code editor:

![Editor](https://github.com/Aashay30/CodeWhiz/blob/main/screenshots/Editor.png)

### **Room Sharing**  
Share the Room ID to invite others and start collaborating!

![Room ID Sharing](https://github.com/Aashay30/CodeWhiz/blob/main/screenshots/Room%20ID%20Sharing.png)

### **Real-Time Collaboration**  
Watch code changes happen live as other users contribute!

![Code Sync](https://github.com/Aashay30/CodeWhiz/blob/main/screenshots/Code%20Sync.png)

### **Join Notification**  
Notification toaster shows up when new user is joined

![Join Notification](https://github.com/Aashay30/CodeWhiz/blob/main/screenshots/Join%20Notification.png)

### **Leave Notification**  
Notification toaster shows up when user leaves the room

![Leave Notification](https://github.com/Aashay30/CodeWhiz/blob/main/screenshots/Leave%20Notification.png)

## 🚀 Run Locally

Want to try it out locally? Follow these simple steps to get up and running!

## Project Structure

The project is organized as follows:

```
codewhiz/
├── public/                 
│   ├── index.html          # Main HTML file
│   ├── favicon.ico         # Favicon for the app
│   ├── manifest.json       # Web app manifest
│   └── robots.txt          # Robots exclusion file
├── src/                    
│   ├── components/         
│   │   ├── Header.js       # Header component
│   │   ├── Footer.js       # Footer component
│   │   └── ...             # Other reusable components
│   ├── pages/              
│   │   ├── HomePage.js     # Home page component
│   │   ├── AboutPage.js    # About page component
│   │   └── ...             # Other page-level components
│   ├── assets/             
│   │   ├── images/         # Image assets
│   │   ├── styles/         # Global and component-specific styles
│   │   └── ...             # Other static assets
│   ├── App.js              # Main application component
│   ├── App.css             # Styles for the App component
│   ├── index.js            # Entry point for React
│   ├── index.css           # Global styles
│   └── reportWebVitals.js  # Performance reporting
├── .gitignore              # Git ignore file
├── package.json            # Project metadata and dependencies
├── package-lock.json       # Lockfile for npm dependencies
├── README.md               # Project documentation
└── node_modules/           # Installed npm packages (auto-generated)
```


1. **Clone the project**

   ```bash
   git clone https://github.com/Aashay30/CodeWhiz
   ```

2. **Navigate to the project directory**

   ```bash
   cd codewhiz
   ```

3. **Install dependencies**

   ```bash
   npm install
   ```

4. **Start the app**

   ```bash
   npm run both
   ```

---

## 🧩 Challenges & Problems Faced During Development

During the development of **CodeWhiz**, several technical and design challenges were encountered. Here’s how I approached and solved them, using a STAR (Situation, Task, Action, Result) format for behavioral interview answers:

---

### 1. Real-Time Code Synchronization Across Users ⏱️

- **Situation:**  
  Multiple users needed to see code changes reflected instantly in a shared editor, regardless of network speed or temporary disconnections.
- **Task:**  
  Ensure all users in a room have a consistent, up-to-date view of the code in real time.
- **Action:**  
  - Integrated **Socket.IO** for real-time, bidirectional communication.
  - Broadcasted code changes as events to all connected users in a room.
  - Implemented reconnection logic to resync the editor state for users who temporarily lost connection.
  - Batched and debounced updates to optimize network usage.
- **Result:**  
  Achieved seamless, real-time code collaboration with minimal latency and robust handling of network interruptions.

---

### 2. Managing Multiple Users and Preventing Edit Conflicts 👥

- **Situation:**  
  Simultaneous editing by multiple users could lead to conflicts and confusion.
- **Task:**  
  Track user actions, display active users, and prevent conflicting edits.
- **Action:**  
  - Assigned unique identifiers (UUIDs) to each user session.
  - Implemented a system to track and display each user’s cursor position in the editor.
  - Added a locking mechanism for critical code sections to avoid race conditions.
  - Displayed a real-time list of connected users in each room.
- **Result:**  
  Enhanced collaboration transparency and minimized editing conflicts, improving the overall user experience.

---

### 3. Optimizing Performance for Real-Time Updates 🚀

- **Situation:**  
  Frequent updates from multiple users could degrade performance and responsiveness.
- **Task:**  
  Keep the app fast and responsive, even with many users or rapid code changes.
- **Action:**  
  - Transmitted only code deltas (changes) instead of the full document.
  - Used **debouncing** to limit update frequency during rapid typing.
  - Leveraged React’s `useMemo` and `useCallback` to prevent unnecessary re-renders.
  - Stress-tested the app under simulated high-load conditions.
- **Result:**  
  Maintained a smooth, lag-free editing experience for all users, even under heavy usage.

---

### 4. Room Management and Security 🔐

- **Situation:**  
  Users needed to create and join rooms securely, with options for public and private collaboration.
- **Task:**  
  Implement secure room creation, joining, and access control.
- **Action:**  
  - Generated unique room IDs using the **UUID** library.
  - Added server-side validation for room IDs and access permissions.
  - Enabled private rooms with password or invite-link protection.
  - Ensured sensitive data was never exposed in client-side code.
- **Result:**  
  Provided a secure and flexible collaboration environment, supporting both public and private coding sessions.

---

### 5. Ensuring Cross-Browser Compatibility 🌐

- **Situation:**  
  Users accessed CodeWhiz from various browsers and devices, requiring consistent functionality everywhere.
- **Task:**  
  Guarantee seamless operation across all major browsers.
- **Action:**  
  - Defined supported browsers using `browserslist` in the project config.
  - Tested and fixed issues on Chrome, Firefox, Safari, and Edge.
  - Used polyfills for unsupported features in older browsers.
- **Result:**  
  Delivered a reliable, consistent experience for all users, regardless of their browser or device.

---

### 6. Enhancing User Experience and Feedback 👍

- **Situation:**  
  Real-time collaboration can be confusing without clear feedback and notifications.
- **Task:**  
  Provide intuitive UI cues and notifications for key events.
- **Action:**  
  - Integrated `react-hot-toast` for real-time notifications (e.g., user join/leave).
  - Designed a clean, responsive UI with React and CSS for usability on all devices.
  - Added helpful error messages and fallback UI for common issues.
- **Result:**  
  Improved user engagement and clarity, making collaboration easy and enjoyable for all skill levels.

---

These challenges demonstrate my ability to build robust, real-time collaborative applications, optimize performance, ensure security, and deliver a polished user experience—skills that are highly valuable for any software engineering role.

---

## 🌟 Key Takeaways from the CodeWhiz Project

---

### 1. Real-Time Web Application Development ⏱️
- Gained hands-on experience building a real-time collaborative code editor using **Socket.IO** for instant, bidirectional communication.
- Learned how to synchronize state across multiple users and handle reconnections gracefully.

---

### 2. Advanced React & Frontend Skills ⚛️
- Built a responsive, interactive UI with **React.js** and **CodeMirror** for a seamless editing experience.
- Utilized React hooks like `useMemo` and `useCallback` to optimize rendering and performance.

---

### 3. Backend Engineering with Node.js & Express.js 🚀
- Designed and implemented a scalable backend to manage rooms, users, and real-time events.
- Ensured efficient handling of WebSocket connections and secure room management.

---

### 4. Performance Optimization & Scalability 🚦
- Optimized real-time updates by sending only code deltas and debouncing rapid changes.
- Stress-tested the application to ensure smooth performance under high user load.

---

### 5. Security & Access Control 🔐
- Implemented secure room creation and joining, including private room support with password/invite protection.
- Ensured sensitive data was handled securely and never exposed on the client side.

---

### 6. Cross-Browser Compatibility 🌐
- Ensured consistent functionality and appearance across all major browsers using polyfills and thorough testing.

---

### 7. Enhanced User Experience 👍
- Integrated real-time notifications and clear UI cues for collaborative actions using `react-hot-toast`.
- Designed a clean, intuitive interface for both technical and non-technical users.

---

### 8. System Design & Project Organization 🏗️
- Structured the project for maintainability and scalability, separating frontend and backend concerns.
- Documented the codebase and project structure for easy onboarding and future enhancements.

---

### 9. Problem-Solving & Debugging Skills 🛠️
- Tackled complex issues like race conditions, synchronization bugs, and performance bottlenecks.
- Developed effective debugging strategies for real-time, multi-user environments.

---

### 10. Communication & Collaboration 🤝
- Improved documentation and communication skills by making the project accessible for other developers.
- Designed features with extensibility and teamwork in mind.

---

## 📝 Summary

The CodeWhiz project provided deep experience in building robust, real-time collaborative applications. It highlights strengths in full-stack development, performance optimization, security, and user-centric design—skills that are highly valuable for modern software engineering roles.
