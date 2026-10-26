# ANAND STUDY TV

Responsive Hindi-first educational website starter for Classes 1–12. Includes 60 original short sample stories (five per class), search and class/category filters, story reader, learning outcomes, vocabulary, show/hide comprehension answers, adjustable font, browser print/PDF, share, SQLite bookmarks, scored quiz, BSEB/SCERT official link entry points, and a protected admin dashboard.

## Local setup
1. Install Node.js 20+.
2. Copy `.env.example` to `.env`.
3. Set `ADMIN_PASSWORD` to a unique password of 12+ characters and `JWT_SECRET` to a random 32+ character secret. Do not commit `.env`.
4. Run `npm install`, `npm run seed`, then `npm start`.
5. Open `http://localhost:3000`. Admin: `http://localhost:3000/admin.html`.

## Included API
- `GET /api/health`
- `GET /api/stories?q=&class=&category=` and `GET /api/stories/:id`
- `GET /api/links`
- `POST /api/auth/login`, `POST /api/auth/logout`, `GET /api/admin/me`
- `GET /api/admin/stories`, `POST/PUT/DELETE /api/admin/stories`
- `POST /api/admin/links`
- `GET/POST/DELETE /api/bookmarks`

## Important before production
This is a functional starter/MVP, not a security-audited production service. Admin story CRUD and link creation are included; a rich quiz-question editor, image/PDF upload UI, password reset, CSRF tokens, audit logs, backup automation, and automated integration tests are not included. Review the code and add appropriate controls before public launch. SQLite is intended for a single persistent app instance; consider PostgreSQL for multi-instance deployment.

Official links are entry points only: https://biharboardonline.com/ and https://scert.bihar.gov.in/textbooks. Verify current syllabus, editions, notices, dates, and model papers directly with official sources before publishing. Do not label original practice material as official BSEB material. The website is independent and not endorsed by BSEB. Stories are original sample content, not textbook reproductions.

For deployment use HTTPS, `NODE_ENV=production`, a strong `JWT_SECRET`, persistent database storage, backups, and a real contact address. Review privacy/copyright pages against your actual data practices. Avoid collecting unnecessary personal information from children. Google Fonts are not used; the layout uses system fonts for faster loading.

## Hosting
For a Node.js host, use build command `npm install` and start command `npm start`; configure the environment variables and persistent disk. Run `npm run seed` once. On a VPS, keep the Node process running with a process manager and put an HTTPS reverse proxy in front.

## Manual smoke test checklist
- Home displays 12 class cards and 60 stories.
- Search by title, then filter by class and category.
- Open a story, enlarge/reduce text, show answers, print to PDF, share.
- Bookmark/unbookmark and reload.
- Complete quiz and confirm score.
- Sign in to admin, create/edit/draft/publish/delete a story, add an HTTPS link.
- Check mobile menu, keyboard focus, and all policy pages.

These are testing instructions, not a claim that tests were executed in this environment.
