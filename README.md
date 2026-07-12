# 🔗 URL Shortener API

A simple and scalable URL Shortener built with **Node.js**, **Express.js**, **MongoDB**, and **Mongoose**. This project generates unique short URLs, redirects users to the original URL, tracks visit history, and provides analytics for each shortened link.

---

## 🚀 Features

- Generate unique short URLs using NanoID
- Redirect users to the original URL
- Store URL data in MongoDB
- Track visit history with timestamps
- Get click analytics for each shortened URL
- RESTful API architecture

---

## 🛠️ Tech Stack

- Node.js
- Express.js
- MongoDB
- Mongoose
- NanoID

---

## 📁 Project Structure

```
URL-Shortener/
│
├── controller/
│   └── url.js
│
├── model/
│   └── url.js
│
├── routes/
│   └── url.js
│
├── connect.js
├── index.js
├── package.json
└── README.md
```

---

## ⚙️ Installation

### Clone the repository

```bash
git clone https://github.com/your-username/url-shortener.git
```

### Navigate to the project

```bash
cd url-shortener
```

### Install dependencies

```bash
npm install
```

### Start MongoDB

Make sure MongoDB is running locally.

```
mongodb://127.0.0.1:27017/short-url
```

### Run the server

```bash
npm start
```

or

```bash
node index.js
```

Server will start on:

```
http://localhost:8001
```

---

## 📌 API Endpoints

### 1. Create Short URL

**POST**

```
/url
```

Request Body

```json
{
    "url": "https://google.com"
}
```

Response

```json
{
    "id": "f9acuYrI"
}
```

---

### 2. Redirect to Original URL

**GET**

```
/:f9acuYrI
```

Automatically redirects to the original website.

---

### 3. Get Analytics

**GET**

```
/url/analytics/:shortId
```

Example

```
/url/analytics/f9acuYrI
```

Response

```json
{
    "totalClick": 5,
    "analytics": [
        {
            "timestamp": 1720777600000
        }
    ]
}
```

---

## 🗄️ Database Schema

```javascript
{
    shortId: String,
    redirectURL: String,
    visitHistory: [
        {
            timestamp: Number
        }
    ]
}
```

---

## 📸 Sample Workflow

1. User submits a long URL.
2. Server generates a unique short ID.
3. Data is stored in MongoDB.
4. User opens the short URL.
5. Server records the visit timestamp.
6. User is redirected to the original URL.
7. Analytics endpoint returns total clicks and visit history.

---

## 🔮 Future Improvements

- User Authentication
- Custom Short URLs
- QR Code Generation
- URL Expiration
- Rate Limiting
- Redis Caching
- Docker Support
- Unit & Integration Testing
- Frontend Dashboard
- Admin Panel

---

## 👨‍💻 Author

**Atul Jaiswal**

- GitHub: https://github.com/atulcodes-tech
- LinkedIn: (https://www.linkedin.com/in/subhkaran-jaiswal/)

---

## 📄 License

This project is licensed under the MIT License.
