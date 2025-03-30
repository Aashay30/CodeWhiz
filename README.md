# 🚀 CodeWhiz

**CodeWhiz** is a real-time collaborative code editor web application that allows multiple users to work on the same code file together. Whether you're working on a team project or simply pair programming, this app lets you create coding rooms, invite others, and collaborate seamlessly in your browser!

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

## 🚧 Key Challenges and Solutions

During the development of **CodeWhiz**, several challenges were encountered. Below is a detailed breakdown of the key challenges and the solutions implemented to overcome them:

### 1. Real-Time Synchronization Issues ⏱️
**Challenge:**  
Ensuring that all users in a room see the same code updates in real time, even with varying network speeds or temporary disconnections.

**Solution:**  
- Implemented **Socket.IO** for real-time, bidirectional communication between the server and clients.
- Used event-based communication to broadcast changes to all connected users in a room.
- Added logic to handle reconnections gracefully by resynchronizing the editor state for users who temporarily lose connection.
- Optimized the frequency of updates by batching changes to reduce network overhead.

### 2. Managing Multiple Users in a Collaborative Environment 👥
**Challenge:**  
Handling multiple users editing the same file simultaneously, including tracking user cursors and preventing conflicts.

**Solution:**  
- Used **unique user identifiers (UUIDs)** to distinguish between users in a session.
- Implemented a cursor tracking system to display each user's cursor position in the editor.
- Added a locking mechanism for critical sections of the code to prevent race conditions.
- Displayed a list of connected users in the room to enhance collaboration transparency.

### 3. Optimizing Performance for Real-Time Updates 🚀
**Challenge:**  
Ensuring the application remains responsive and performant, even with a large number of users or frequent updates.

**Solution:**  
- Minimized the size of data sent over WebSocket connections by transmitting only deltas (changes) instead of the entire document.
- Used **debouncing** to limit the frequency of updates sent to the server during rapid typing.
- Optimized frontend rendering by leveraging **React's useMemo** and **useCallback** hooks to prevent unnecessary re-renders.
- Tested the application under simulated high-load conditions to identify and resolve bottlenecks.

### 4. Room Management and Security 🔐
**Challenge:**  
Allowing users to create and join rooms securely while preventing unauthorized access to private rooms.

**Solution:**  
- Generated unique room IDs using the **UUID** library.
- Added server-side validation to ensure only valid room IDs are accepted.
- Implemented private room functionality by requiring a password or invite link for access.
- Used HTTPS for secure communication and ensured sensitive data (e.g., room passwords) is never exposed in client-side code.

### 5. Handling Cross-Browser Compatibility 🌐
**Challenge:**  
Ensuring the application works seamlessly across different browsers and devices.

**Solution:**  
- Used **browserslist** in the `package.json` file to define supported browsers and ensure compatibility during the build process.
- Tested the application on major browsers (Chrome, Firefox, Safari, Edge) and resolved any inconsistencies.
- Leveraged **polyfills** for features not natively supported in older browsers.

### 6. User Experience Enhancements 👍
**Challenge:**  
Providing a smooth and intuitive user experience, especially for non-technical users.

**Solution:**  
- Added **toast notifications** (using `react-hot-toast`) to inform users of key events, such as when someone joins or leaves a room.
- Designed a clean and responsive UI using **React** and **CSS** to ensure usability on both desktop and mobile devices.
- Included helpful error messages and fallback mechanisms for common issues, such as invalid room IDs or server downtime.

## Key Takeaways

Building **CodeWhiz** was a valuable learning experience that allowed me to enhance my technical skills and gain hands-on experience with real-world software development challenges. Below are the key takeaways from this project:

---

### 1. **Hands-On Experience with Real-Time Web Applications ⏱️**
- Developed a real-time collaborative code editor that synchronizes changes across multiple users instantly.
- Gained practical experience in implementing **real-time communication** using **Socket.IO** for bidirectional data flow.
- Learned how to handle challenges like synchronization, reconnections, and managing multiple users in a shared environment.

---

### 2. **Improved Understanding of WebSocket Communication 🌐**
- Explored the inner workings of **WebSocket protocols** and how they enable low-latency, persistent connections.
- Implemented event-driven communication between the client and server to broadcast updates efficiently.
- Optimized WebSocket performance by batching updates and minimizing data payloads.

---

### 3. **Enhanced Skills in React.js and Frontend Development ⚛️**
- Built a responsive and interactive user interface using **React.js**.
- Leveraged **React Router** for seamless navigation between pages and dynamic room creation.
- Integrated **CodeMirror** for a feature-rich code editor with syntax highlighting and cursor tracking.

---

### 4. **Backend Development with Node.js and Express.js 🚀**
- Designed and implemented a scalable backend using **Node.js** and **Express.js**.
- Managed room creation, user connections, and real-time data synchronization on the server side.
- Ensured secure and efficient handling of WebSocket events for multiple concurrent users.

---

### 5. **System Design and Architecture 🏗️**
- Designed a modular and scalable architecture to support real-time collaboration.
- Gained experience in separating frontend and backend concerns for better maintainability.
- Learned how to deploy and manage a full-stack application using modern tools like **Vercel**.

---

### 6. **Problem-Solving and Debugging 🔍**
- Tackled challenges such as handling race conditions, managing user sessions, and optimizing performance.
- Debugged complex issues related to real-time synchronization and cross-browser compatibility.
- Improved my ability to identify bottlenecks and implement efficient solutions.

---

### 7. **Collaboration and Communication Skills 🤝**
- Documented the project thoroughly to make it accessible for other developers.
- Designed the application with scalability and extensibility in mind, enabling future enhancements.
- Gained experience in presenting technical projects effectively through detailed documentation and demos.



