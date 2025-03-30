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
