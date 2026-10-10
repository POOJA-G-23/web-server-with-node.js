# Basic Node.js Web Server for Static HTML Pages

## 🎯 Aim
To develop a basic Node.js web server to deliver static HTML pages using Express.

---

## 📁 Project Structure
```text
web server with node js/
├── public/
│   ├── index.html       # Home page
│   ├── about.html       # About page
│   ├── contact.html     # Contact page
│   └── style.css        # Modern responsive design system
├── node_modules/        # Installed npm dependencies
├── package.json         # Project manifest and scripts
├── package-lock.json    # Locked dependency tree
├── server.js            # Node.js Express server script
└── README.md            # Lab documentation
```

---

## 🛠️ Step-by-Step Procedure Followed

### 1. Initialize Your Project
Initialized the Node.js project manifest:
```bash
npm init -y
```

### 2. Install Required Dependencies
Installed the Express framework:
```bash
npm install express
```

### 3. Create HTML & Static Assets
Created the `public/` directory containing:
- [index.html](file:///c:/Users/pooja/OneDrive/Desktop/Application%20Development%20lab/web%20server%20with%20node%20js/public/index.html): Home page with hero section & overview cards.
- [about.html](file:///c:/Users/pooja/OneDrive/Desktop/Application%20Development%20lab/web%20server%20with%20node%20js/public/about.html): System architecture & workflow details.
- [contact.html](file:///c:/Users/pooja/OneDrive/Desktop/Application%20Development%20lab/web%20server%20with%20node%20js/public/contact.html): Interactive contact form with submission feedback.
- [style.css](file:///c:/Users/pooja/OneDrive/Desktop/Application%20Development%20lab/web%20server%20with%20node%20js/public/style.css): Modern dark-mode styling with glassmorphism.

### 4. Create Node.js Server
Created [server.js](file:///c:/Users/pooja/OneDrive/Desktop/Application%20Development%20lab/web%20server%20with%20node%20js/server.js) to configure Express:
```javascript
const express = require('express');
const path = require('path');

const app = express();
const PORT = process.env.PORT || 3000;

// Serve static files from the public directory
app.use(express.static(path.join(__dirname, 'public')));

// Specific routes to deliver HTML pages
app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

app.get('/about', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'about.html'));
});

app.get('/contact', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'contact.html'));
});

// Start server listening
app.listen(PORT, () => {
    console.log(`Server is running on port ${PORT}`);
    console.log(`Open in browser: http://localhost:${PORT}`);
});
```

---

## 🚀 How to Run the Server

1. **Start the server:**
   ```bash
   node server.js
   ```
   *(or `npm start`)*

2. **Access in your web browser:**
   - **Home Page**: [http://localhost:3000/](http://localhost:3000/) or [http://localhost:3000/index.html](http://localhost:3000/index.html)
   - **About Page**: [http://localhost:3000/about](http://localhost:3000/about) or [http://localhost:3000/about.html](http://localhost:3000/about.html)
   - **Contact Page**: [http://localhost:3000/contact](http://localhost:3000/contact) or [http://localhost:3000/contact.html](http://localhost:3000/contact.html)
