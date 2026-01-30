# AI Nutritionist – Image Upload Frontend

## What the project does

This project is a lightweight **frontend-only web application** that allows users to upload food images from their device and send them to a remote backend for prediction.

The application:

* Lets users select or capture an image using their device camera
* Sends the image to a hosted backend API using `fetch` and `FormData`
* Displays upload status and prediction results returned by the backend

This project focuses purely on **client-side image upload and API communication**, making it ideal for testing and demonstrations.

---

## Why this project is useful

* Demonstrates how to upload images from a browser to a backend API
* Shows real-world usage of `FormData` and `fetch`
* Supports mobile camera capture using the `capture` attribute
* Can be used as a standalone frontend for any image-based ML backend
* Useful for learning frontend–backend integration without frameworks

---

## Project structure

```
.
├── index.html     # Frontend HTML and JavaScript
├── styles.css     # Styling for the UI
├── README.md
```

---

## Tech Stack

* HTML5
* CSS3
* Vanilla JavaScript

---

## How to get started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ai-nutritionist-image-upload.git
cd ai-nutritionist-image-upload
```

---

### 2. Run the frontend

No build or installation is required.

You can either:

* Open `index.html` directly in a browser, or
* Serve it using a local HTTP server (recommended):

```bash
python -m http.server 8000
```

Then open:

```
http://localhost:8000
```

---

## Backend integration

The frontend sends the image to the following API endpoint:

```
POST https://backend-oqae.onrender.com/upload
```

### Request details

* Content-Type: multipart/form-data
* Field name: `file`
* Value: image file

### Example JavaScript request

```js
const formData = new FormData();
formData.append("file", file);

fetch("https://backend-oqae.onrender.com/upload", {
  method: "POST",
  body: formData
});
```

---

## Expected API response

```json
{
  "filename": "image.jpg",
  "size_kb": 210,
  "prediction": "pizza"
}
```

The frontend displays the filename and prediction returned by the backend.

---

## UI features

* Fullscreen background image
* Glassmorphism-style container
* Mobile-friendly image capture support
* Upload status and prediction message display

---

## Where to get help

* MDN Web Docs: [https://developer.mozilla.org/](https://developer.mozilla.org/)
* Fetch API documentation: [https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)

---

## Maintainer

Prashanth T

---

## Future improvements

* Image preview before upload
* Loading indicator during upload
* Better error messages for network failures
* Configurable backend URL
* Responsive layout improvements
