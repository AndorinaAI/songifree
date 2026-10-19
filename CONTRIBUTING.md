# Contributing to Songifree 🎵

First off, thank you for considering contributing to Songifree! Whether you are fixing a bug, adding support for a new streaming platform, improving the OBS overlay, or refining documentation, your help makes live streaming music better for everyone.

---

## 🌿 Branching Strategy

To keep releases stable, we follow a two-branch workflow:

- **`main`**: The production-ready branch. Only tagged, tested releases are merged here. Direct pushes to `main` are restricted.
- **`dev`**: The active development branch. **All feature branches, bug fixes, and Pull Requests MUST target `dev`!**
- **Feature Branches**: Branch off from `dev` using clear prefixes:
  - `feature/add-youtube-music`
  - `fix/kick-websocket-reconnect`
  - `ui/glassmorphic-overlay-theme`
  - `docs/setup-guide`

```text
main   ─────────────●──────────────────────● (v0.2.0 Release)
                     \                    /
dev    ────────●──────●──────────●───────●─── (Active development)
                \               /
feature          ●─────────────● (Your PR targets dev)
```

---

## 🚀 Getting Started with Local Development

### Prerequisites
- [Node.js](https://nodejs.org/) v18.0.0 or higher (v20 LTS recommended)
- [npm](https://www.npmjs.com/) v9.0.0+
- A Spotify Premium account (required by the Spotify Web API for playback control)
- A Spotify Developer App ([Developer Dashboard](https://developer.spotify.com/dashboard))

### Setup Steps
1. **Fork and Clone the Repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/songifree.git
   cd songifree
   git checkout dev
   ```

2. **Create your feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Install Dependencies:**
   ```bash
   npm install
   ```

4. **Setup Environment Variables:**
   ```bash
   cp .env.example .env
   ```
   Open `.env` and fill in your Spotify Client ID and Client Secret.

5. **Start Development Server:**
   ```bash
   npm run dev
   ```
   - Broadcaster Dashboard: `http://localhost:3000`
   - OBS Browser Source Overlay: `http://localhost:3000/overlay`

---

## 📝 Commit Conventions

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

- `feat:` A new feature for the user or platform integration
- `fix:` A bug fix
- `docs:` Documentation only changes
- `style:` Formatting, missing semicolons, etc. (no functional code changes)
- `refactor:` A code change that neither fixes a bug nor adds a feature
- `test:` Adding or updating tests
- `chore:` Maintenance, updating dependencies, build configuration

**Example:**
```text
feat(kick): handle channel reconnect when websocket drops
fix(spotify): refresh expired access token before queueing track
docs(readme): clarify twitch oauth scope requirements
```

---

## 🧪 Testing Guidelines

Before creating a Pull Request:
1. Run type checking:
   ```bash
   npm run typecheck
   ```
2. Run automated tests:
   ```bash
   npm test
   ```
3. Test locally in your browser and OBS Studio (test song requests from mock chat or real chat).

---

## 📥 Submitting a Pull Request

1. Push your branch to your GitHub fork:
   ```bash
   git push origin feature/your-feature-name
   ```
2. Open a Pull Request on GitHub.
3. **Verify the base branch is `dev`** (NOT `main`).
4. Fill out the PR template completely with details of what was changed and how you tested it.
5. Wait for the automated CI workflow to pass. Maintainers will review your PR and provide constructive feedback!

---

## 💬 Community & Questions

Have an idea or question before you start coding? Open a discussion in [GitHub Discussions](https://github.com/AndorinaAI/songifree/discussions). We'd love to chat!
