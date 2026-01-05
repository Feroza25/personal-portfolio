# Feroza Y - Personal Portfolio Website

A modern, responsive portfolio website showcasing my skills, projects, and achievements in Cloud Computing, Cybersecurity, and Software Development.

## 🌟 Features

- **Responsive Design** - Works perfectly on desktop, tablet, and mobile devices
- **Modern UI/UX** - Beautiful gradient designs with smooth animations
- **Interactive Navigation** - Smooth scrolling with active section highlighting
- **Contact Form** - Direct email integration for easy communication
- **Resume Download** - One-click resume download functionality
- **Project Showcase** - Detailed project cards with technologies used
- **Social Links** - Direct links to LinkedIn, GitHub, and email

## 📁 Project Structure

```
portfolio/
├── index.html          # Main HTML file
├── css/
│   └── style.css      # All styles and animations
├── js/
│   └── script.js      # JavaScript functionality
├── assets/
│   └── resume.pdf     # Your resume PDF file
└── README.md          # This file
```

## 🚀 How to Run Locally

1. **Download/Clone the project**
   ```bash
   # If you have git installed
   git clone <your-repo-url>
   
   # Or simply download the ZIP file and extract it
   ```

2. **Add your resume**
   - Place your resume PDF file in the `assets/` folder
   - Name it `resume.pdf` (or update the path in index.html)

3. **Open the website**
   - Simply double-click on `index.html`
   - Or right-click and open with your browser
   - Or use a local server:
     ```bash
     # Using Python 3
     python -m http.server 8000
     
     # Using Node.js http-server
     npx http-server
     ```

## 🌐 Deploy to Netlify

### Method 1: Drag and Drop (Easiest)

1. Go to [Netlify](https://www.netlify.com/)
2. Sign up or log in
3. Drag your entire `portfolio` folder to the Netlify drop zone
4. Your site will be live in seconds!

### Method 2: GitHub Integration

1. Create a GitHub repository
2. Push your code:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
3. Go to Netlify → "New site from Git"
4. Connect your GitHub repository
5. Deploy!

### Method 3: Netlify CLI

1. Install Netlify CLI:
   ```bash
   npm install -g netlify-cli
   ```

2. Deploy:
   ```bash
   cd portfolio
   netlify deploy --prod
   ```

## ⚙️ Customization Guide

### Update Personal Information

1. **Email Addresses**
   - Find all instances of `yferoza12@gmail.com` in:
     - `index.html` (multiple places)
     - `js/script.js` (sendEmail function)
   - Replace with your email

2. **Social Links**
   - Update LinkedIn URL: `https://linkedin.com/in/feroza-y-351390307`
   - Update GitHub URL: `https://github.com/Feroza25`

3. **Projects**
   - Edit project cards in `index.html`
   - Add your own project descriptions, technologies, and features

4. **Skills**
   - Modify skill categories and tags in the Skills section
   - Add or remove skills as needed

5. **Colors and Theme**
   - Edit CSS variables in `style.css`:
     ```css
     :root {
         --primary-color: #a855f7;    /* Purple */
         --secondary-color: #ec4899;  /* Pink */
         /* Change these to your preferred colors */
     }
     ```

### Add More Sections

To add new sections:

1. Add section in `index.html`:
   ```html
   <section id="your-section" class="your-section">
       <!-- Your content -->
   </section>
   ```

2. Add navigation link:
   ```html
   <a href="#your-section" class="nav-link">Your Section</a>
   ```

3. Add styles in `style.css`

## 📧 Contact Form Setup

The contact form currently uses `mailto:` which opens the user's email client. For a proper backend form:

### Option 1: Formspree (Recommended - Free)

1. Go to [Formspree](https://formspree.io/)
2. Sign up and create a form
3. Get your form endpoint
4. Replace the `sendEmail()` function in `script.js`:

```javascript
function sendEmail() {
    const name = document.getElementById('name').value;
    const email = document.getElementById('email').value;
    const message = document.getElementById('message').value;
    const statusDiv = document.getElementById('form-status');
    
    if (!name || !email || !message) {
        statusDiv.innerHTML = '<p class="error">Please fill in all fields!</p>';
        return;
    }
    
    fetch('YOUR_FORMSPREE_ENDPOINT', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ name, email, message })
    })
    .then(response => {
        if (response.ok) {
            statusDiv.innerHTML = '<p class="success">Message sent successfully!</p>';
            document.getElementById('name').value = '';
            document.getElementById('email').value = '';
            document.getElementById('message').value = '';
        } else {
            statusDiv.innerHTML = '<p class="error">Failed to send. Please try again.</p>';
        }
    })
    .catch(() => {
        statusDiv.innerHTML = '<p class="error">Network error. Please try again.</p>';
    });
}
```

### Option 2: Netlify Forms

1. Add `netlify` attribute to your form in `index.html`:
   ```html
   <form name="contact" netlify>
   ```
2. Netlify will automatically handle form submissions

### Option 3: EmailJS

1. Sign up at [EmailJS](https://www.emailjs.com/)
2. Follow their setup guide
3. Integrate their SDK

## 🎨 Browser Compatibility

- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Opera

## 📱 Mobile Responsive

The website is fully responsive and tested on:
- 📱 Mobile (320px - 480px)
- 📱 Tablet (481px - 768px)
- 💻 Desktop (769px+)

## 🐛 Troubleshooting

### Issue: Resume doesn't download
- **Solution**: Make sure `resume.pdf` exists in the `assets/` folder

### Issue: Contact form doesn't work
- **Solution**: Check browser console for errors. Consider using Formspree or Netlify Forms

### Issue: Animations not working
- **Solution**: Ensure JavaScript is enabled in your browser

### Issue: Hamburger menu doesn't open on mobile
- **Solution**: Check that `script.js` is properly linked in `index.html`

## 📈 Performance Tips

1. **Optimize Images** (if you add any)
   - Use WebP format
   - Compress images before uploading
   - Use tools like TinyPNG

2. **Minify Files for Production**
   ```bash
   # CSS
   npx clean-css-cli style.css -o style.min.css
   
   # JavaScript
   npx terser script.js -o script.min.js
   ```

3. **Enable Caching**
   - Netlify automatically handles this

## 🔒 Security

- No sensitive data is stored
- All external links open in new tabs
- Email addresses are not directly exposed to scrapers in mailto links

## 📝 License

This project is open source and available for personal use. Feel free to customize it for your own portfolio!

## 🤝 Support

If you encounter any issues or have questions:
- Email: yferoza12@gmail.com
- LinkedIn: [Feroza Y](https://linkedin.com/in/feroza-y-351390307)
- GitHub: [Feroza25](https://github.com/Feroza25)

## 🎉 Credits

Created with ❤️ by Feroza Y

---

**Good luck with your portfolio! 🚀**
=======
# personal-portfolio
This repository contains the source code for my Personal Portfolio Website, designed to showcase my projects, technical skills, experience, and learning journey as a developer. The portfolio serves as a central place where I highlight my work, demonstrate my problem-solving abilities, and share the technologies I actively use and explore.
>>>>>>> 02e134e48a9c35f1afd7d5cd28ebe3ef86fa6f0b
