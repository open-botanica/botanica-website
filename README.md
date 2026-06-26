# Botanica Website

Minimal static website scaffold for a plain `html/css/js` project.

## Structure

- `src/index.html` is the page entry point.
- `src/styles.css` is the external stylesheet hook.
- `src/script.js` is the external JavaScript hook.
- `Dockerfile` serves `src/` with `nginx` on port `80`.

## Run locally

Serve the `src/` directory directly:

```bash
python3 -m http.server 8080 -d src
```

Then open `http://localhost:8080`.

## Run with Docker

```bash
docker build -t botanica-website .
docker run --rm -p 8080:80 botanica-website
```

## GitHub publishing

This repository includes `.github/workflows/publish-image.yml`.

- Push to `main` or `master` to build and publish the Docker image to `ghcr.io/<owner>/<repo>`.
- Create a tag like `v1.0.0` to publish a versioned image tag.
- No custom secrets are required for GHCR publishing with the included workflow.
