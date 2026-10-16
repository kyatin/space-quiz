# Space Exploration Quiz

A dependency-free, ten-question quiz about space exploration, built with HTML,
CSS, and JavaScript in a single `index.html` file. It features instant answer
feedback, a progress bar, results, and a personal best saved in your browser.
The responsive interface supports light and dark themes, keyboard navigation,
and reduced-motion preferences.

## Play online

Visit [Space Exploration Quiz](https://kyatin.github.io/space-quiz/).

## Run locally

Open `index.html` directly in your browser. No installation or build is needed.

Alternatively, serve the repository with Python 3:

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>. Stop the server with `Ctrl+C`.

## Deployment

GitHub Pages is configured to use **GitHub Actions** in the repository's
**Settings > Pages > Build and deployment > Source**.

The workflow in `.github/workflows/pages.yml` packages only `index.html` as the
site artifact. Pull requests targeting `main` check that packaging succeeds
without deploying. Pushes to `main` deploy the artifact to GitHub Pages; you can
also run the workflow manually from the Actions tab on `main`.

If the app gains a build step or additional assets, update the workflow's
`Prepare site` step to put the complete generated website in `_site`.
