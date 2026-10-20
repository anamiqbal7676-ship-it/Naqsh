# Release verification

Prepared 20 October 2026.

## Change scope

Only the red-background image of the woman in white was removed from the website. Its collection entry and `art-00.webp` were deleted. Layout, CSS, application logic, text, and all remaining site files were preserved. The 24 remaining collection artworks automatically populate the dome, galleries, and image questions.

## Checks completed

- `npm run build` passed, including JavaScript syntax, six artist records, 24 artwork records, and local image/font references.
- All 31 retained WebP files were decoded successfully.
- All remaining published website files were compared with the pre-change source. Only the requested image removal changed the website.
- Exported `dist` files match the updated website byte for byte.
- Browser: landing page rendered with local fonts and no broken loaded images; dome pause control worked; clicking the dome enlarged an artwork in the viewer.
- Browser: archive search returned Zubeida Agha; artist navigation, maroon milestone styling, and View the Collection were exercised.
- Browser: the gallery contained 24 images; artist filtering and artwork enlargement worked. Every one of the 24 gallery images loaded successfully.
- Browser: a complete six-question quiz reached its results screen.
- The final ZIP was CRC-tested and its bundled website files were compared with the source.

## Deployment configuration

`vercel.json` sets the framework to Other, runs `npm run build`, and serves `dist`. The project has no third-party npm dependencies, API keys, server-side functions, database, or environment-variable requirements. Images, fonts, styles, scripts, and animations are bundled locally.

## Limits

A deployment in the user's Vercel/GitHub accounts was not performed. Browser QA used the managed static preview; the included local Node development server was syntax-checked. Existing mobile CSS is preserved; a separate mobile-device session was not run for this release. Reduced-motion settings intentionally suppress automatic animation.
