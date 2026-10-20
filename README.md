# Adshaya R | Portfolio (React + Node.js)

## Structure
```
portfolio/
├── package.json            root scripts (run client and server together)
├── .prettierrc / .editorconfig
├── client/                 React (Vite)
│   ├── public/Adshaya_R_Resume.pdf
│   └── src/
│       ├── data.js         ALL content lives here
│       ├── index.css       design tokens and styles
│       ├── components/     page sections + ui/ (Section, Chips, Bullets)
│       ├── hooks/          useActiveSection (scroll-aware navigation)
│       └── utils/api.js    contact API call
└── server/src/             Express API
    ├── config/env.js       environment settings
    ├── routes/contact.js   POST /api/contact (rate limited)
    ├── validators/         input validation
    ├── services/mailer.js  email sending
    ├── app.js              middleware + routes
    └── server.js           entry point
```

## Run in VS Code
1. Install Node.js 18+ and open the `portfolio` folder in VS Code.
2. Open the terminal (Ctrl + `) and run:
```
npm run install:all
cd server && cp .env.example .env && cd ..      (Windows: copy .env.example .env)
npm run dev
```
Frontend: http://localhost:5173  |  API: http://localhost:5000

Recommended VS Code extensions: ESLint, Prettier, ES7+ React Snippets.

## Useful commands
| Command | Purpose |
|---|---|
| `npm run dev` | Start frontend and backend together |
| `npm run lint` | Check code quality (ESLint) |
| `npm run format` | Auto-format all code (Prettier) |
| `npm run build` | Production build of the frontend |

## Real emails
Google Account > Security > enable 2-Step Verification > create an App Password.
Put it in `server/.env` as `MAIL_PASS` and your Gmail as `MAIL_USER`.
Without these, messages are printed in the server terminal (good for testing).

## Customise
- Content: `client/src/data.js` (add `repo` and `demo` links to each project)
- Resume: replace `client/public/Adshaya_R_Resume.pdf` (keep the file name)
- Colors and fonts: top of `client/src/index.css`

## Deploy
1. Push to GitHub.
2. Render (backend): root `server`, build `npm install`, start `npm start`; add the .env values and set `CLIENT_ORIGIN` to your frontend URL.
3. Vercel (frontend): root `client`, framework Vite; set `VITE_API_URL` to your Render URL.
