# Canada Capital Computer Computing Coding Club

A free, open-source website for the Computer Computing Coding Club featuring sign-up, authentication, chat, coding playground, and more.

## Features

- ✅ **User Authentication** — Sign up, log in, and manage profiles with password hashing
- ✅ **Live Chat** — Real-time messaging with typing indicators, emoji reactions, and user list
- ✅ **Chat Server Tutorial** — Step-by-step guide to build real-time chat with Node.js & Socket.IO
- ✅ **Code Playground** — Write and preview HTML, CSS, and JavaScript with 7 themes
- ✅ **Project Sharing** — Share coded projects via URL hash encoding
- ✅ **Responsive Design** — Works on desktop, tablet, and mobile

## File Structure

```
├── index.html              # Homepage
├── SignUp.html            # User registration
├── Login.html             # User login
├── Profile.html           # User profile & settings
├── Chat.html              # Chat room with features
├── ChatServer.html        # Tutorial for building chat servers
├── Playground.html        # HTML/CSS/JS code editor
├── mystyle.css            # Global styles
└── README.md              # This file
```

## Getting Started Locally

### 1. Clone or Download the Repository

```bash
git clone https://github.com/HopofPlayz/Canada-Capital-Computer-Computing-Coding-Club.git
cd Canada-Capital-Computer-Computing-Coding-Club
```

Or download the ZIP file and extract it.

### 2. Start a Local Server

**Option A: Python 3 (Built-in)**
```bash
python3 -m http.server 8000
# Open http://localhost:8000 in your browser
```

**Option B: Node.js with `http-server`**
```bash
npm install -g http-server
http-server
# Open http://localhost:8080 in your browser
```

**Option C: VS Code Live Server**
- Install the "Live Server" extension in VS Code
- Right-click on `index.html` → "Open with Live Server"

### 3. Test the Features

- **Sign up** → Click "Join today!" and create an account
- **Log in** → Use your credentials on the Login page
- **Chat** → Send messages, add emoji reactions, see typing indicators
- **Playground** → Write HTML/CSS/JS, switch themes, share projects
- **Profile** → Edit name, change password, delete account

## Deploying to GitHub Pages

### Step 1: Create a GitHub Repository

1. Go to [github.com](https://github.com) and log in
2. Click **New** to create a new repository
3. Name it: `Canada-Capital-Computer-Computing-Coding-Club`
4. Check **Public** so it's accessible to everyone
5. Click **Create repository**

### Step 2: Push Your Code

```bash
git init
git add .
git commit -m "Initial commit: Add website files"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/Canada-Capital-Computer-Computing-Coding-Club.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username.

### Step 3: Enable GitHub Pages

1. Go to your GitHub repository
2. Click **Settings** → **Pages** (left sidebar)
3. Under "Build and deployment":
   - **Source**: Select `Deploy from a branch`
   - **Branch**: Select `main` and `/root` folder
4. Click **Save**
5. Wait 1-2 minutes for the site to build
6. Your site is now live at: `https://YOUR_USERNAME.github.io/Canada-Capital-Computer-Computing-Coding-Club/`

### Step 4: Update Links (Optional)

If you want to update the homepage link to point to the GitHub Pages URL, edit `index.html`:

```html
<h1><a href="https://YOUR_USERNAME.github.io/Canada-Capital-Computer-Computing-Coding-Club/">Canada Capital Computer Computing Coding Club</a></h1>
```

## Deploying to Other Platforms

### Netlify (Recommended for Easy Setup)

1. Go to [netlify.com](https://netlify.com) and sign up
2. Click **Add new site** → **Import an existing project**
3. Connect your GitHub account
4. Select your repository
5. Deploy settings:
   - **Build command**: (leave empty)
   - **Publish directory**: `/` (root)
6. Click **Deploy**
7. Your site is live at a Netlify URL (e.g., `https://your-site.netlify.app`)

### Vercel

1. Go to [vercel.com](https://vercel.com) and sign up
2. Click **New Project**
3. Import your GitHub repository
4. Click **Deploy**
5. Your site is live instantly

### Heroku (with Backend Support)

If you want to add a backend (e.g., for real database storage):

```bash
# Create a Procfile
echo "web: node server.js" > Procfile

# Deploy
git push heroku main
```

See the [Chat Server Tutorial](ChatServer.html) for backend setup.

### Traditional Web Hosting (cPanel, Shared Hosting, VPS)

1. **Export files**: Use SFTP or File Manager in cPanel
2. **Upload** all `.html` and `.css` files to your `public_html` directory
3. **Access** via your domain: `https://yourdomain.com`

**Note**: Features that use `localStorage` (chat, playground, authentication) work client-side only. For production, integrate a backend database.

## How Features Work

### Authentication (Client-Side Demo)
- Passwords are hashed using `crypto.subtle.digest('SHA-256')`
- User data stored in `localStorage` (NOT production-secure)
- For production: Use JWT tokens, HTTPS, and server-side authentication

### Chat (Real-Time Local)
- Messages stored in `localStorage.ccc_messages`
- Typing indicators and user sessions tracked locally
- For production: Use WebSockets (Socket.IO) with backend

### Playground (Client-Side Editor)
- Code runs in an `iframe` sandbox (`allow-scripts`)
- Projects shareable via URL hash encoding (base64)
- No syntax highlighting yet; can add CodeMirror for enhanced editing

## Customization

### Change Club Name
Edit `index.html` and `mystyle.css`:
```html
<h1>My Awesome Club</h1>
```

### Add Custom Colors
Edit `mystyle.css`:
```css
.button {
  background: #your-color;
}
```

### Add More Pages
Create new `.html` files and link them from `index.html`:
```html
<a href="Events.html" class="button">Events</a>
```

## Troubleshooting

### "Website won't load"
- Ensure you're using a local server (Python, Node, Live Server)
- Don't open `.html` files directly in the browser (some features won't work)
- Check browser console for errors (F12 → Console)

### "Chat/Playground not working"
- Clear browser cache and localStorage: `localStorage.clear()` in console
- Ensure JavaScript is enabled in your browser
- Try a different browser or incognito mode

### "Can't log in"
- Sign up first if you haven't already
- Check that passwords match (case-sensitive)
- Clear `localStorage` and try again

### "Share link doesn't work"
- Ensure the URL hash isn't truncated when copying
- Base64-encoded projects can be long; use a URL shortener if needed

## Production Checklist

Before going live:

- [ ] Set up real user authentication (Firebase, Auth0, or custom backend)
- [ ] Use a database (MongoDB, PostgreSQL) instead of localStorage
- [ ] Add SSL/HTTPS certificate (most hosts provide free SSL)
- [ ] Enable CORS if adding a backend API
- [ ] Test on multiple browsers and devices
- [ ] Set up analytics (Google Analytics, Plausible)
- [ ] Add privacy policy and terms of service
- [ ] Test all forms and user flows
- [ ] Optimize images and assets for performance

## Contributing

Want to improve this website? Fork the repo and submit a pull request!

Ideas:
- Add course materials or tutorials
- Create lesson pages
- Add project gallery
- Integrate real chat backend
- Build mobile app

## License

This project is open source and available under the MIT License.

## Support

For issues or questions:
1. Check the [GitHub Issues](https://github.com/HopofPlayz/Canada-Capital-Computer-Computing-Coding-Club/issues)
2. Open a new issue with details
3. Contact the club organizers

---

**Built with ❤️ by the Canada Capital Computer Computing Coding Club**
