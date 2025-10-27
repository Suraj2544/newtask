# GitHub Actions Daily Commit Workflow Setup Guide

## Overview
This guide provides instructions for the DevSync daily repository update automation workflow configured for email: **21f3000813@ds.study.iitm.ac.in**

## Files Created

### 1. Workflow File: `.github/workflows/daily-commit.yml`
The main GitHub Actions workflow file that:
- **Runs on Schedule:** Daily at 09:00 UTC using cron syntax `0 9 * * *`
- **Can be Manually Triggered:** via `workflow_dispatch` for testing
- **Includes Email in Steps:** Multiple step names include `21f3000813@ds.study.iitm.ac.in`
- **Creates Commits:** Automatically adds entries to `activity.log`
- **Pushes Changes:** Automatically pushes commits back to the repository

### 2. Supporting Files
- `README.md` - Project documentation
- `activity.log` - Log file that tracks automated updates
- `.gitignore` - Standard Git ignore patterns

## Workflow Details

### Schedule Configuration
```yaml
schedule:
  - cron: '0 9 * * *'
```
- **Minute:** 0 (specific, not wildcard)
- **Hour:** 9 UTC (specific, not wildcard)
- **Day of Month:** * (every day)
- **Month:** * (every month)
- **Day of Week:** * (every day of the week)

### Key Steps

1. **Checkout Repository**
   - Uses `actions/checkout@v4`
   - Fetches full history for proper commit tracking

2. **Configure Git User**
   - Sets git user name: "DevSync Automation"
   - Sets git user email: "21f3000813@ds.study.iitm.ac.in"

3. **Create Daily Commit**
   - Generates a timestamp in UTC format
   - Appends entry to `activity.log`
   - Creates a commit with timestamp and email reference

4. **Push Changes**
   - Automatically pushes commit to the repository's current branch

5. **Log Completion**
   - Records successful workflow execution

## Email Integration

The email **21f3000813@ds.study.iitm.ac.in** appears in:
- ✅ Workflow name: "Daily Repository Update - 21f3000813@ds.study.iitm.ac.in"
- ✅ Step name: "Configure git user for 21f3000813@ds.study.iitm.ac.in"
- ✅ Step name: "Create daily update commit for 21f3000813@ds.study.iitm.ac.in"
- ✅ Step name: "Log workflow completion for 21f3000813@ds.study.iitm.ac.in"
- ✅ Git user email configuration
- ✅ Commit message includes email reference

## How to Use

### 1. Initialize Git Repository Locally
```bash
cd c:\Users\Asus\Desktop\poopee
git init
git add .
git commit -m "Initial commit with GitHub Actions workflow"
```

### 2. Create GitHub Repository
- Go to https://github.com/new
- Create a new repository
- Do not initialize with README (we already have one)

### 3. Connect and Push
```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git push -u origin main
```

### 4. Enable GitHub Actions
- Go to your repository on GitHub
- Navigate to **Actions** tab
- Enable GitHub Actions if not already enabled

### 5. Trigger Workflow
Option A: **Wait for Schedule** - Workflow will run automatically at 09:00 UTC daily

Option B: **Manual Trigger**
- Go to **Actions** tab
- Select "Daily Repository Update - 21f3000813@ds.study.iitm.ac.in" workflow
- Click "Run workflow" → "Run workflow"

### 6. Monitor Execution
- Navigate to **Actions** tab
- Click on the latest workflow run
- View step execution logs in real-time
- Verify commit appears in repository history

## Verification Steps

After the workflow runs, verify:

1. **Workflow Appears in Actions**
   - ✅ Most recent action in your repository
   - ✅ Status shows as "Passed" (green checkmark)

2. **Commit Created**
   - ✅ New commit appears in repository history
   - ✅ Commit message includes timestamp and email reference
   - ✅ Author shows as "DevSync Automation"

3. **Activity Log Updated**
   - ✅ `activity.log` file contains new entries
   - ✅ Entry includes UTC timestamp

4. **Timeline**
   - ✅ Commit created within 5 minutes of workflow run
   - ✅ Matches workflow execution time in Actions tab

## Troubleshooting

### Workflow Not Running
- Check branch is set to the default branch in workflow settings
- Ensure GitHub Actions is enabled in repository settings
- Verify cron schedule is correct for your timezone

### Commit Not Appearing
- Check repository permissions are correctly set (`contents: write`)
- Verify git configuration in workflow is correct
- Check push step is targeting the correct branch

### Email Not Appearing in Commits
- Verify git config email matches: `21f3000813@ds.study.iitm.ac.in`
- Check commit message includes email reference
- Confirm step names include the email address

## Repository URL Format

Once created, your repository URL will be:
```
https://github.com/YOUR_USERNAME/YOUR_REPO
```

Example:
```
https://github.com/devsync-team/daily-automation
```

## Additional Notes

- The workflow respects GitHub's rate limits and best practices
- Each commit is automatically timestamped for audit purposes
- The workflow can be manually triggered anytime from the Actions tab
- Activity logs provide a complete record of all automated updates
- Commits are cryptographically signed and traceable to GitHub Actions

---

**Workflow Created:** October 27, 2025
**Email:** 21f3000813@ds.study.iitm.ac.in
**Schedule:** Daily at 09:00 UTC (no wildcards)
