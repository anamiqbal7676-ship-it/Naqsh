# Naqsh website

The website is ready for VS Code, GitHub, and Vercel. The requested red-background portrait of a woman in white has been removed everywhere. All other site images and fonts are included in `dist/assets`.

## Open in VS Code

1. Extract this ZIP completely.
2. Open the **naqsh-website** folder in VS Code. This is the folder containing `package.json`, `vercel.json`, and `dist`.
3. Install Node.js 20 or newer if it is not already installed.
4. In the VS Code terminal, run:

```sh
npm install
npm run check
npm run dev
```

Open the local or network URL printed in the terminal. The development server listens on all network interfaces by default, so the network-IP URL works too. If the default port is busy, choose another:

```sh
npm run dev -- --port 3001
```

Use Ctrl+C to stop the server. Do not move or rename individual asset files.

## Push to GitHub

Use VS Code's Source Control panel to initialize a repository, commit all project files, and publish to your GitHub account. The entire **dist** folder must be committed, including `dist/assets`. It is deliberately not ignored.

Alternatively, in the terminal:

```sh
git init
git add .
git commit -m "Add Naqsh website"
git branch -M main
```

Create an empty repository on GitHub, then use the remote URL GitHub gives you:

```sh
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your own repository URL before running it. Do not upload only the ZIP to GitHub; push the extracted files.

## Deploy on Vercel

Import the GitHub repository as a new Vercel project. `vercel.json` provides the settings:

| Setting | Value |
| --- | --- |
| Root Directory | The folder containing `package.json` and `vercel.json` (normally repository root) |
| Framework Preset | Other |
| Build Command | `npm run build` |
| Output Directory | `dist` |
| Environment Variables | None required |

Click Deploy. Future GitHub pushes can use Vercel's normal automatic deployments.

The build validates image and font paths, profile data, and JavaScript before publishing the static files. No API keys, database, backend server, or ChatGPT connection is needed by the deployed website. Hash routes such as `/#/archive` work with a normal static deployment and page refresh.

## What stays with the website

- Six artist profiles and all six portrait images.
- 24 retained collection artworks.
- Full-width rotating dome, dragging, pause/rotate controls, and artwork enlargement.
- Moving image strip, navigation hover effects, gallery, filters, and six-question varied quiz.
- All local fonts and image files. No temporary download links or external image/font hosting.

The site has 31 WebP files (including retained source assets not currently displayed) and 11 local font files. Keep all of them in the repository.

## File map

- `dist/index.html`: shared page shell and artwork dialog.
- `dist/app.js`: routes, dome, gallery, filters, and quiz.
- `dist/data.js`: artist profiles and artwork associations.
- `dist/style.css`: design, responsive layout, and animations.
- `dist/assets/`: images and local typography.
- `scripts/check.mjs`: dependency-free deployment validation.
- `scripts/serve.mjs`: local development server.
- `vercel.json`: Vercel build/output settings.

This is a static website. External biography/source links remain external links. Reduced-motion preferences intentionally pause automatic motion; the dome's play and rotate controls remain available.

## Verification scope

See `VERIFICATION.md` for the checks completed before packaging. A deployment in your Vercel account has not been performed; the included configuration is prepared for that step.
