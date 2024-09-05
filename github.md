## GitHub Cheatsheet

### How to git push using GitHub token on the command line

```bash
# Initialize a new Git repository
git init

# Add all files to staging
git add .

# Commit the changes
git commit -m "first commit"

# Rename the default branch to 'main'
git branch -M main

# Set the remote URL with the GitHub token
git remote set-url origin https://<token>@github.com/<username>/<repo>.git

# Push changes to the 'main' branch
git push origin main
