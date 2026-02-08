# Homework-6: Interactive Contact Form 📬

![Contact Form Preview](images/preview.png) <!-- Assuming a preview image exists or can be added -->

## 📋 Overview
This project is a simple, animated contact form built with pure HTML and CSS. It's designed as a homework assignment (Homework-6) to demonstrate floating labels, form animations, responsive design, and basic styling without any JavaScript. The form includes fields for name, email, and message, with a send button. It's deployed automatically to GitHub Pages via a GitHub Actions workflow.

**Key Features**:
- 🌟 **Floating Labels**: Labels animate and float above inputs when filled or focused.
- 🎥 **Animations**: Smooth entry animation for the form and hover effects on the button.
- 📱 **Responsive Design**: Adjusts layout for mobile devices (max-width: 768px).
- 🔒 **Validation**: Basic HTML5 validation for required fields and email format.
- 🚀 **Auto-Deployment**: Uses GitHub Actions to deploy static content to GitHub Pages.
- 🎨 **Custom Styling**: Modern, clean design with shadows, rounded corners, and color schemes (teal background, light inputs).

This is a static page—no backend, database, or actual email sending. For real functionality, integrate with services like Formspree or EmailJS.

## 🛠️ Project Structure
The project is organized as a simple static web page with minimal files. Here's the file tree:

```
Homework-6/
├── .gitattributes          # Git configuration for text normalization
├── .github/
│   └── workflows/
│       └── static.yml      # GitHub Actions workflow for deployment to GitHub Pages
├── index.html              # Main HTML file containing the form structure
├── style.css               # CSS stylesheet for styling and animations
├── images/
│   └── icon.png            # Favicon icon (referenced in HTML)
└── README.md               # This documentation file (add it to your repo)
```

- **Root Files**: Core HTML and CSS for the page.
- **.github/workflows**: Contains deployment automation.
- **images**: Directory for assets like icons (icon.png is used as favicon).

No JavaScript files, databases, or external dependencies are present. This keeps the project lightweight and focused on HTML/CSS fundamentals.

## ⚙️ Setup and Commands
Since this is a static site, setup is straightforward. No build tools or servers are required locally.

### Prerequisites
- Git installed.
- A GitHub account for deployment.

### Installation and Local Development
1. **Clone the Repository**:
   ```
   git clone https://github.com/your-username/Homework-6.git
   cd Homework-6
   ```

2. **Open Locally**:
   - Simply open `index.html` in any web browser (e.g., Chrome, Firefox).
   - No server needed, but for live preview with auto-reload, use tools like Live Server in VS Code.

3. **Edit and Test**:
   - Modify `index.html` for structure changes.
   - Update `style.css` for styling.
   - Test responsiveness by resizing the browser or using dev tools (F12 > Toggle device toolbar).

### Deployment Commands
Deployment is automated via GitHub Actions. No manual commands needed beyond pushing to GitHub.

1. **Push to Main Branch**:
   ```
   git add .
   git commit -m "Update contact form"
   git push origin main
   ```

2. **Manual Trigger** (via GitHub):
   - Go to your repo > Actions tab > Select "Deploy static content to Pages" > Run workflow.

After pushing, the site deploys to `https://your-username.github.io/Homework-6/`. Check the Actions tab for build status.

### Other Useful Commands
- **Lint CSS** (optional, requires csslint installed via npm):
  ```
  npm install -g csslint
  csslint style.css
  ```
- **Validate HTML**:
  Use online tools like W3C Validator or run locally if you have htmlhint:
  ```
  npm install -g htmlhint
  htmlhint index.html
  ```

No complex commands since there's no backend or build process.

## 📝 Detailed Code Explanation
### index.html
This is the core structure file. It defines a simple HTML page with a form.

- **Head Section**:
  - Meta tags for charset and viewport (responsive).
  - Title: "Homework 6 - Contact form".
  - Links to `style.css` and favicon `images/icon.png`.

- **Body Section**:
  - A `<div class="form --animated">` container with animation class.
  - Inputs:
    - `<input type="text" id="name" ...>`: Name field (required).
    - `<input type="email" id="email" ...>`: Email field (required, validates email format).
    - `<textarea id="message" ...>`: Message field (required, resizable with scrollbar styling).
  - Labels: Floating labels linked via `for` attributes.
  - Button: `<button class="form-button btn btn--animated">Send</button>` with hover/animation effects.

No JavaScript—interactivity comes from CSS pseudo-classes like `:not(:placeholder-shown)` and `:focus`.

### style.css
Handles all visuals, animations, and responsiveness.

- **Global Resets**: `* { margin: 0; padding: 0; box-sizing: border-box; }` for consistent layout.
- **Body Styling**: Black background, flex-centered form.
- **Form Container**: Teal background, shadow, rounded, padded.
- **Labels and Inputs**:
  - Labels start hidden/opaque and animate up when input is filled/focused.
  - Inputs: Light background, border effects on focus (green for valid, orange for invalid).
  - Textarea: Custom scrollbar styling.
- **Button**:
  - Rounded, uppercase, with hover (translate up, shadow) and active states.
- **Animations**:
  - `@keyframes moveInBottom`: Fades in and slides up the form on load.
- **Media Query**: For screens ≤768px, reduces sizes and paddings for mobile.

Frequently Used CSS Techniques:
- **Transitions**: `transition: all 0.5s ease-in-out;` for smooth changes.
- **Pseudo-Classes**: `:focus`, `:not(:placeholder-shown)`, `:hover`, `:active`.
- **Variables**: None used (vanilla CSS), but could be refactored with CSS vars.
- **Flexbox**: For centering and layout.

No functions or templates since this is pure CSS—no preprocessors like SCSS.

### .gitattributes
Simple config:
- `* text=auto`: Ensures LF line endings for text files across platforms.

### .github/workflows/static.yml
GitHub Actions workflow for deployment.

- **Triggers**: On push to `main` or manual dispatch.
- **Permissions**: Read contents, write to Pages.
- **Jobs**:
  - Checkout code.
  - Setup Pages.
  - Upload entire repo as artifact.
  - Deploy to GitHub Pages.
- Environment: Points to `github-pages` with output URL.

This automates hosting without manual uploads.

## 🗄️ Databases and Data Storage
This project is fully static—no databases, storage, or data persistence.

- **No Databases**: No SQL/NoSQL integration (e.g., no MongoDB, PostgreSQL).
- **No Stored Data**: Form submissions aren't handled (browser-only validation). To add, integrate JS with a backend/API.
- **Potential Extensions**:
  - If adding JS: Use LocalStorage for temporary data (e.g., { name: string, email: string, message: string }).
  - Sample Type: JSON object like `{ "name": "John Doe", "email": "john@example.com", "message": "Hello!" }`.
  - But currently: Zero storage.

## 🚧 Limitations and Improvements
- **No Real Submission**: Form doesn't send data—add JS for AJAX.
- **Accessibility**: Add ARIA labels for better screen reader support.
- **Enhancements**: Dark mode toggle, JS validation, or theme switcher.

## 🤝 Contributing
Fork the repo, make changes, and submit a PR! Use issues for bugs or ideas.

## 📄 License
MIT License—free to use and modify.

---

Built with ❤️ by [Your Name]. Deployed on GitHub Pages.