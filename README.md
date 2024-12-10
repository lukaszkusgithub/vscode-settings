# Backup and Restore Visual Studio Code Settings and Extensions

This guide explains how to backup your Visual Studio Code settings and extensions to GitHub and restore them when needed.

## Backup Instructions

### 1. Export Settings and Keybindings
1. Open Visual Studio Code.
2. Navigate to:
   - `File` (or `Code` on macOS) → `Preferences` → `Settings`.
   - Click the icon to open the settings JSON file.
3. Save the `settings.json` file.
4. Navigate to:
   - `Preferences` → `Keyboard Shortcuts`.
   - Click the icon to open the keybindings JSON file.
5. Save the `keybindings.json` file.

### 2. Export Extensions
Run the following command in the terminal:

```bash
code --list-extensions > extensions.txt
```

This command generates a file named `extensions.txt` containing a list of installed extensions.

### 3. Create a GitHub Repository
1. Go to [GitHub](https://github.com/) and create a new repository.
   - Name it something like `vscode-backup`.
   - Set it to public or private as per your preference.
2. Clone the repository to your local machine:

```bash
git clone https://github.com/your-username/vscode-backup.git
```

### 4. Add Files to the Repository
1. Copy `settings.json`, `keybindings.json`, and `extensions.txt` into the cloned repository folder.
2. Optionally, add a `README.md` file with instructions.
3. Commit and push the changes to GitHub:

```bash
# Navigate to the repository folder
cd vscode-backup

# Add files
git add settings.json keybindings.json extensions.txt

# Commit changes
git commit -m "Backup VS Code settings and extensions"

# Push to GitHub
git push origin main
```

---

## Restore Instructions

### 1. Clone the Repository
Clone your backup repository to the new machine:

```bash
git clone https://github.com/your-username/vscode-backup.git
```

### 2. Restore Settings and Keybindings
Copy `settings.json` and `keybindings.json` to the appropriate directory:

- **macOS**: `~/Library/Application Support/Code/User/`
- **Linux**: `~/.config/Code/User/`
- **Windows**: `%APPDATA%\Code\User\`

### 3. Reinstall Extensions
Run the following command to reinstall all extensions from `extensions.txt`:

```bash
cat extensions.txt | xargs -n 1 code --install-extension
```

---

## Notes
- Ensure you have Git installed on your system before using this guide.
- If you face any issues, consult the [VS Code documentation](https://code.visualstudio.com/docs).
- Customize this process to include additional files or configurations if needed.

Happy coding! 🚀
