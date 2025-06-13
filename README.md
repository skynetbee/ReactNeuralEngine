# 🚀 React App Deployment using XAMPP

This repository contains a React-based project ready for deployment using XAMPP's `htdocs`. Follow the steps below to download, extract, and run the app locally.

---

## 📦 Download the Release

1. Go to the [Releases](https://github.com/skynetbee/ReactNeuralEngine/releases/download/13June2025/devenv.zip) section of this repository.
2. Download the latest `.zip` file (e.g., `devenv.zip`).

---

## 🧩 Prerequisites

Make sure you have the following installed:

- **[XAMPP](https://www.apachefriends.org/index.html)** (for running a local Apache server)
- A browser (Chrome, Firefox, etc.)

---

## 📁 Set Up with XAMPP

1. Extract the downloaded ZIP file.
2. Rename the folder if needed (e.g., `my-react-app`).
3. Move the entire folder into your XAMPP `htdocs` directory:
   ```
   C:\xampp\htdocs\my-react-app
   ```

4. Start **Apache** from the XAMPP Control Panel.

---

## 🌐 Run the App

Open your browser and navigate to:
```
http://localhost/my-react-app
```

You should now see your React app running locally through XAMPP.

---

## 🛠 Troubleshooting

- **Blank Page?**  
  Make sure your `index.html` is inside a `build` folder or directly inside the project root.
  
- **404 Errors?**  
  Check if file paths in `index.html` use relative paths (e.g., `./static/...`) instead of absolute paths (`/static/...`).

---

## 📌 Notes

- This deployment method is suitable for testing or demo purposes only.
- For production-grade deployments, consider hosting your React app on [Vercel](https://vercel.com), [Netlify](https://www.netlify.com), or any static hosting provider.

---

## 🤝 License

This project is licensed under the [MIT License](./LICENSE).
