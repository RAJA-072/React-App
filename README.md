
# **React Firebase App**  

This project is a simple web application built with **React.js** and **Firebase**. It demonstrates the integration of Firebase services like **Authentication**, **Firestore** (database), **Storage**, and **Hosting** with a React frontend.

---

## **Features**

- **User Authentication**: Sign up, log in, and log out using Firebase Authentication (Email/Password, Google, etc.).
- **Firestore Database**: Real-time CRUD operations.
- **Firebase Storage**: Upload and manage files.
- **Firebase Hosting**: Deploy the React app on Firebase.

---

## **Prerequisites**

Ensure you have the following installed:

- **Node.js**: [Download](https://nodejs.org/)
- **Firebase CLI**: `npm install -g firebase-tools`
- **React**: `npx create-react-app my-app`

---

## **Setup Instructions**

### 1. **Clone the Repository**
```bash
git clone https://github.com/your-repo/react-firebase-app.git
cd react-firebase-app
```

### 2. **Install Dependencies**
```bash
npm install
```

### 3. **Firebase Project Configuration**

1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/).
2. Add a web app to your Firebase project and copy the configuration object.
3. Create a `.env` file in your project root and add Firebase credentials:

```bash
REACT_APP_API_KEY=your-api-key
REACT_APP_AUTH_DOMAIN=your-auth-domain
REACT_APP_PROJECT_ID=your-project-id
REACT_APP_STORAGE_BUCKET=your-storage-bucket
REACT_APP_MESSAGING_SENDER_ID=your-messaging-sender-id
REACT_APP_APP_ID=your-app-id
```

### 4. **Initialize Firebase in the Project**

Create a `firebase.js` file in the `src` folder:
```javascript
import { initializeApp } from 'firebase/app';
import { getAuth } from 'firebase/auth';
import { getFirestore } from 'firebase/firestore';
import { getStorage } from 'firebase/storage';

const firebaseConfig = {
  apiKey: process.env.REACT_APP_API_KEY,
  authDomain: process.env.REACT_APP_AUTH_DOMAIN,
  projectId: process.env.REACT_APP_PROJECT_ID,
  storageBucket: process.env.REACT_APP_STORAGE_BUCKET,
  messagingSenderId: process.env.REACT_APP_MESSAGING_SENDER_ID,
  appId: process.env.REACT_APP_APP_ID
};

const app = initializeApp(firebaseConfig);
export const auth = getAuth(app);
export const db = getFirestore(app);
export const storage = getStorage(app);
```

---

## **Running the Application**

### 1. **Start the Development Server**
```bash
npm start
```
Access the app at `http://localhost:3000`.

### 2. **Build for Production**
```bash
npm run build
```

---

## **Deploying to Firebase Hosting**

1. **Login to Firebase CLI:**
   ```bash
   firebase login
   ```

2. **Initialize Firebase Hosting:**
   ```bash
   firebase init
   ```
   - Select Hosting.
   - Use the `build` directory as your public directory.
   - Configure as a single-page app (`y` for SPA).

3. **Deploy the App:**
   ```bash
   firebase deploy
   ```

---

## **Project Structure**
```
react-firebase-app/
├── public/             # Static files
├── src/                # Source code
│   ├── components/     # Reusable React components
│   ├── firebase.js     # Firebase configuration
│   ├── App.js          # Main App component
│   └── index.js        # Entry point
├── .env                # Environment variables
└── package.json        # Project metadata
```

---

