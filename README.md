# Farooj Almasi — Admin App · الفروج الماسي

Branch & owner admin dashboard for **Farooj Almasi** (الفروج الماسي). Single-file
HTML + React app. Staff receive and manage live orders, menu, branches, customers,
loyalty, reports, and printing. Orders placed in the Farooj Almasi customer app arrive
here in real time.

This is a brand replica of the Broast Al Bahr admin app, rebuilt for Farooj Almasi as a
**separate company with its own Firebase project** (shared only with the Farooj Almasi
customer app — never with Al-Bahr).

## Setup

1. Fill in your Firebase config inside `index.html` (search `TODO(Farooj Almasi)` — use
   the **same Almasi** project as the customer app, not Al-Bahr's).
2. Complete the one-time console setup in `FIREBASE_SETUP.md` (enable Auth, create the
   owner account + role doc, publish `firestore.rules`).
3. Serve `index.html` from any static host (or open locally once keys are set).

## Status at launch

- Menu, branches, and receipt contact lines start **empty** — add real data from the app.
- Firebase config is a **placeholder** until the new Almasi project keys are pasted in.

## Theme

Green primary + gold accent, derived from the Al-Masi logo.
