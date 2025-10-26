# WeebOwO Discord Bot Website

## Setup Instructions

### 1. Install Required Packages

First, install Flask for the API server:

```bash
pip install flask flask-cors
```

### 2. Add Your Bot Profile Picture

Place your `bot_pfp.png` image in the `website` folder.

### 3. Start Your Bot

Run your bot as normal:

```bash
python bot.py
```

The bot will automatically start an API server on `http://localhost:5000` that serves the server count.

### 4. Open the Website

Simply open `website/index.html` in your browser. The server count will automatically load from your running bot!

## How It Works

- Your bot runs a Flask API server in the background (port 5000)
- The website fetches the server count from `http://localhost:5000/api/stats`
- Every time someone opens the website, it gets the live server count
- The count automatically updates when your bot joins/leaves servers

## Hosting Online

If you want to host this website online:

1. **Host your bot** on a service like Railway, Heroku, or a VPS
2. **Update the API URL** in `script.js` line 8 to your bot's public URL:
   ```javascript
   const response = await fetch('https://your-bot-url.com/api/stats');
   ```
3. **Upload the website** to GitHub Pages, Netlify, or Vercel

## API Endpoint

The bot exposes one endpoint:

- `GET /api/stats` - Returns:
  ```json
  {
    "server_count": 5,
    "user_count": 1234
  }
  ```

Enjoy! :3
