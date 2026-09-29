# Admitly Ontario — interactive prototype

A React admissions dashboard based on the supplied design. Runs entirely in the browser. No database, API key or paid service required.

## Try it immediately

Open `demo.html` in Chrome, Edge or Firefox. This standalone file includes the built React app, CSS and sample avatar; no install is needed to try it. Edits to the React source require rebuilding. The same demo is also supplied separately as `Admitly-demo.html`.

## Run on your computer

1. Install Node.js LTS if you do not have it.
2. Extract this folder and open it in VS Code.
3. Open Terminal → New Terminal, inside this folder.
4. Run `npm install`, then `npm run dev`.
5. Open the local URL printed in the terminal.

## Put it on GitHub Pages

Upload the CONTENTS of this folder to the root of your repository. Include `.github/workflows/deploy.yml` (GitHub Desktop is easiest because browser uploads can miss hidden folders).

Commit and push to `main`. In your repository, go to **Settings → Pages → Source → GitHub Actions**. The included workflow builds and publishes the site. Check the **Actions** tab for progress, then open the site URL shown in **Settings → Pages**.

Do not choose “Deploy from a branch” for the raw React source. React needs the build step in the included workflow.

The Vite base is relative and page navigation uses URL hashes, so repository subpaths and page refreshes work on GitHub Pages. It also works on Vercel: framework Vite, build `npm run build`, output `dist`.

## Included interactions

- Dashboard: profile, grades, chance cards, recommended programs and deadlines link into detailed pages/dialogs.
- Explore Programs: search, field/chance/co-op filters, sort, save/unsave, detail dialogs and application tracking.
- My Universities: persistent shortlist, program details and application balance.
- Applications: status changes, notes, checklists, add/remove tracked applications.
- AI Advisor: scripted contextual demo responses, suggested questions and custom text input. No actual AI API.
- Course Planner: edit grades/statuses, add/remove courses, sample prerequisite checks.
- Deadlines: list/calendar views, add/delete dates and mark complete.
- Profile: editable identity, interests, preferences and reset demo.
- Calculator: try grades, see a projected average, and apply changes to your profile.
- Header: global search, keyboard shortcut, notifications, profile menu.
- Responsive layout, mobile navigation and keyboard-accessible dialogs.

## Demo limitations

Program requirements, deadlines and admission scores are illustrative samples, not official data or validated predictions. Real submissions and user authentication are not implemented. The displayed percentages match the reference at the initial sample average and move with changes in grades using a demo formula.

The supplied reference has an inconsistent top-six average: its displayed grades average 92.3%, rather than 93.8%. This prototype computes the average correctly, so the initial display is 92.3%.

Changes are stored in localStorage on the same browser/device. They do not sync between users or devices. Use Profile → Reset demo to restore the sample data. Do not enter sensitive personal information into a shared demo.

## Files

- `src/main.jsx`: React pages and interactions
- `src/model.js`: sample data and demo calculations/responses
- `src/styles.css`: responsive design
- `.github/workflows/deploy.yml`: GitHub Pages publishing
- `public/reference.png`: supplied mockup used as a CSS crop for the sample avatar

To add Supabase later, replace the local data loading/saving layer; the UI can stay. Connect a real advisor through a server endpoint so API keys remain private. Keep real admissions estimates separate from this demo formula.
