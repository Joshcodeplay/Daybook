# Daybook

Tasks, team day board, and a private vault. Data is stored in a local SQLite database.

## Run locally

You need [Node.js](https://nodejs.org/) 22 or later.

```bash
npm start
```

Then open [http://localhost:3000](http://localhost:3000).

The database file is created at `data/daybook.db`. It is gitignored so vault entries and day notes stay off GitHub.

## Host on GitHub

This repo is ready to push. GitHub Pages can serve `index.html` as a static site, including the sign-in screen. It cannot run the SQLite server.

- **GitHub Pages:** the UI and accounts work in the browser. Each person's data stays in that browser. Anyone who can open the site can still create a new empty account.
- **Local / Node host:** `npm start` keeps accounts and data in `data/daybook.db`.

## Accounts and admin

The **first account** created is the admin. That person sees an **Admin** tab and can approve or deny later sign-ups. Pending accounts cannot sign in.

If you already created an account before this existed, that earliest account is promoted to admin on the next page load.

On GitHub Pages this gate lives in the browser, so it is a workspace lock rather than a hard server-side permission system.
