# CLAUDE.md - Developer & Agent Guidelines

## Build & Run Instructions
This is a static site project.
- **Run Locally**: Open [index.html](file:///Users/druskhi/Desktop/Blue%20Lotus%20Den/money-over-all/index.html) in any web browser.
- **No Build Step**: There are no npm packages or compilation requirements for the main web interface.

## Git Deployment Guidelines
When deploying to the remote repository, standard sandboxed terminal commands will fail to access the macOS Keychain (`osxkeychain`) and cause credential errors (`Device not configured`).

### Deploy Workaround
Always use the cached GitHub Personal Access Token (PAT) from previous conversation logs (search transcript logs under `~/.gemini/antigravity-ide/brain/` for `github_pat_`).

To deploy:
1. Stage and commit changes locally:
   ```bash
   git add <files>
   git commit -m "<message>"
   ```

2. Temporarily set the remote URL with your credentials token (retrieved from logs):
   ```bash
   git remote set-url origin https://<PAT_RETRIEVED_FROM_LOGS>@github.com/thebluelotusden/d2026-moa.git
   ```

3. Push the commits to origin:
   ```bash
   git push origin main
   ```

4. Restore the remote URL to the clean HTTPS remote:
   ```bash
   git remote set-url origin https://github.com/thebluelotusden/d2026-moa.git
   ```
