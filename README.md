# SAFETUBE

**WATCH WHAT MATTERS.**

SAFETUBE is a browser-based video-sharing prototype designed to be published as a static site on GitHub Pages.

## Run locally

1. Download `safetube.html`.
2. Open it in a modern browser.
3. SAFETUBE stores prototype data in that browser's local storage.

## Publish with GitHub Pages (no terminal or Node.js required)

1. Create a GitHub repository.
2. In the repository, choose **Add file → Upload files**.
3. Upload `safetube.html`.
4. Rename `safetube.html` to `index.html` in GitHub, or upload a copy named `index.html`.
5. Open **Settings → Pages**.
6. Under **Build and deployment**, choose **Deploy from a branch**, select the default branch and `/ (root)`, then save.
7. Wait for GitHub Pages to publish the site. Open the URL shown in the Pages settings.

The family dashboard route is `/#/admin`.

## Important limitations

This build is a local-browser prototype, not a production multi-user video platform.

- GitHub Pages hosts static files; it does not provide a database, server-side authentication, video processing, or moderation services.
- Accounts, comments, likes, reports, playlists, and settings are stored locally in one browser. They are not shared between family members or devices.
- The Family Admin dashboard is intentionally reachable at `/#/admin` without a separate login, as requested. **It is not secure.** Anyone who can open the public site can open the dashboard, and local JavaScript cannot enforce secure permissions.
- Uploaded video data currently uses browser object URLs and is not a durable cloud upload system. Do not rely on local uploads surviving browser restarts or being available on other devices.
- The sample-video view counts are sample content, not live platform analytics.
- Passwords in this prototype are not protected by production-grade authentication. Do not use a real password.

## What is needed for a real shared platform

A production SAFETUBE needs a hosted backend with:
- Server-enforced authentication and role/permission checks.
- A database for users, channels, videos, comments, subscriptions, playlists, and reports.
- Object storage for video and thumbnail files.
- Upload validation and video processing/transcoding.
- Server-side moderation/report workflows and audit logs.
- Secure admin authorization enforced by the backend (not by hiding a route or checking a PIN in frontend code).

A hosted service such as Supabase can provide parts of this foundation, but it must be configured with appropriate database policies, storage policies, and server-side authorization. Never put service-role or other secret keys in this HTML file.
