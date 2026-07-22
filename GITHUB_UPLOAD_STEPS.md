# GitHub upload steps (Veilforge 2.7.0)

## 1) Create the repository on GitHub
- Go to https://github.com/new
- Repository name suggestion: `Veilforge`
- Visibility: Public or Private (your choice)
- Do **not** initialize with README/.gitignore/license (already present locally)

## 2) Link local repo to GitHub
Run these commands from this folder:

```powershell
cd "D:\_JDR_Ressources\Veilforge 2.7.0\Veilforge-main-github-upload"
"C:\Program Files\Git\cmd\git.exe" remote add origin https://github.com/<YOUR_USER>/<YOUR_REPO>.git
"C:\Program Files\Git\cmd\git.exe" push -u origin main
```

## 3) If GitHub asks authentication
- Use browser sign-in or a Personal Access Token (PAT).
- If asked for password in terminal, use PAT instead of account password.

## 4) Verify
- Open your repository page on GitHub.
- Confirm branch `main` and files are visible.

## Optional next push workflow
```powershell
"C:\Program Files\Git\cmd\git.exe" add .
"C:\Program Files\Git\cmd\git.exe" commit -m "Your message"
"C:\Program Files\Git\cmd\git.exe" push
```
