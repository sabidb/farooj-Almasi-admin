# Farooj Almasi Admin — Agent instructions

الفروج الماسي · Farooj Almasi branch/admin app. This is a rebrand/replica of the
Broast Al Bahr admin app (`sabidb/Al-bahr-admin`) for a **separate company** with
its **own, separate Firebase project** (shared with the Farooj Almasi customer app,
never with Al-Bahr). If you ever see `broast-al-bahr` project ids or Al-Bahr Firebase
keys in this repo, that is a bug — fix it.

## App version

`const APP_VERSION` at the top of `index.html` is the single source of truth for the
visible admin-app version. It is rendered:

- as a tiny `v<x.y.z>` stamp fixed above the bottom navigation on every tab,
- on the login screen under the sign-in card,
- inside the System settings section (`[["Version", "Farooj Almasi Admin v" + …]]`).

### Auto-bump policy — do this on every commit that changes `index.html`

Before committing any code change to `index.html`, bump `APP_VERSION` in place (semver):

- **patch** (`x.y.Z`) — every non-trivial fix, small tweak, copy change, wiring update. Default.
- **minor** (`x.Y.0`) — a new user-visible feature or a new admin section/tab.
- **major** (`X.0.0`) — breaking change to the Firestore schema or a rewrite of a full flow.

Never skip the bump. Never batch — one commit that changes `index.html` = one version bump.

Docs-only commits (README, CLAUDE.md, comments-only) do not bump the version.

Current baseline established: `1.0.0`.

## Theme (from the logo)

Green primary + gold accent, derived from the Al-Masi logo. Brand red `#E60000`/`#E10600`
was remapped to green `#2E7D32`; brand gradient partners and gold → `#E0A526`. Semantic
status colors (danger reds, success emerald, status oranges/blues) are unchanged.

## Firebase

Config lives inline in `index.html` (search `TODO(Farooj Almasi)`). Fill in the **same
Almasi Firebase project** the customer app uses. `firestore.rules` must stay in sync with
`farooj-almasi-customer-app/firestore.rules`. See `FIREBASE_SETUP.md` for first-time setup.

## Branching

Work on `main` unless the user tells you otherwise. Fresh repo; pushing `main` deploys
once the user wires up hosting (static single-file app — any static host works).
