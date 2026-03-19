# 📖 How to Submit Your Assignments — Complete Guide

> **This guide walks you through EVERYTHING — from setting up Git to submitting your assignment via a Pull Request.**
>
> Follow each step exactly. Screenshots are described so you know what to look for on GitHub.

---

## 🧰 One-Time Setup (Do This Only Once)

### 1. Create a GitHub Account

- Go to [github.com](https://github.com) and sign up
- Use a **professional username** (this will be on your portfolio!)
  - ✅ Good: `rahul-kumar`, `priya2026`, `mohammed-ali`
  - ❌ Bad: `xXxDarkLord`, `cutegirl123`, `asdfgh`

### 2. Install Git on Your Computer

| OS | How to Install |
|----|---------------|
| **Windows** | Download from [git-scm.com](https://git-scm.com/) → Run the installer → Keep all defaults → Click "Install" |
| **Mac** | Open Terminal → Type `git --version` → It will prompt to install if needed |
| **Linux** | Open Terminal → Run `sudo apt install git` |

### 3. Configure Git (Tell Git Who You Are)

Open your terminal (Git Bash on Windows, Terminal on Mac/Linux) and run:

```bash
git config --global user.name "Your Full Name"
```
```bash
git config --global user.email "your_email@example.com"
```

> ⚠️ Use the **same email** you used to create your GitHub account.

**Example:**
```bash
git config --global user.name "Rocky Kumar"
git config --global user.email "rocky@example.com"
```

To verify it worked:
```bash
git config --global user.name
git config --global user.email
```

---

## 🍴 Step 1: Fork the Repository

**What is a Fork?** A fork is your **personal copy** of the repository on GitHub. You make changes in your copy, then request to merge them into the original.

### How to Fork:

1. Go to the original repo: **[github.com/infinitethoughts7/ai-adventure](https://github.com/infinitethoughts7/ai-adventure)**
2. Look at the **top-right corner** of the page
3. Click the **"Fork"** button
4. On the next page, click **"Create fork"** (keep all defaults)
5. Done! You now have your own copy at `github.com/YOUR_USERNAME/ai-adventure`

> 💡 You only need to fork **once**. After that, you always work from your fork.

---

## 📥 Step 2: Clone Your Fork to Your Computer

**What is Cloning?** Cloning downloads the repository from GitHub to your local computer so you can work on it.

Open your terminal and run:

```bash
git clone https://github.com/YOUR_USERNAME/ai-adventure.git
```

> 🔁 Replace `YOUR_USERNAME` with your actual GitHub username.

**Example (if your username is `rocky2026`):**
```bash
git clone https://github.com/rocky2026/ai-adventure.git
```

**How to find your clone URL:**
1. Go to **your forked repo** on GitHub (`github.com/YOUR_USERNAME/ai-adventure`)
2. Click the green **"<> Code"** button
3. Make sure **HTTPS** is selected
4. Copy the URL
5. Use it in the `git clone` command

---

## 📂 Step 3: Navigate Into the Project

After cloning, you'll see a new folder called `ai-adventure`. Go into it:

```bash
cd ai-adventure
```

Then go into the `submissions` folder:

```bash
cd submissions
```

> 💡 **Where am I?** Run `pwd` (Mac/Linux) or `cd` (Windows) to see your current location. You should see something like `/home/yourname/ai-adventure/submissions`.

---

## 📁 Step 4: Create Your Personal Folder

Create a folder with your name and roll number using this **exact format**:

```
FirstName_LastName_RollNumber
```

### Naming Rules:
- Use **PascalCase** — capitalize the first letter of each word
- Use **underscores** `_` to separate parts
- **No spaces**, no hyphens, no special characters

### Examples:

✅ **Correct:**
```
Rocky_Ganji_B230001
Priya_Sharma_B230045
Mohammed_Ali_B230112
```

❌ **Wrong:**
```
rocky kumar b230001        ← spaces, no capitals
ROCKY_KUMAR_B230001        ← ALL CAPS is not PascalCase
rocky-kumar-B230001        ← hyphens instead of underscores
Rocky Kumar_B230001        ← space between first and last name
rocky_kumar_b230001        ← all lowercase
```

### Create the folder:

```bash
mkdir Rocky_Ganji_B230001
```

### Go into your folder:

```bash
cd Rocky_Ganji_B230001
```

> ⚠️ **Double-check your folder name before proceeding!** Renaming later is messy. Get it right the first time.

---

## 📄 Step 5: Add Your Assignment File

### Real Example: Submitting `python_fundamentals.ipynb`

Let's say you've been given an assignment — a Jupyter Notebook called `python_fundamentals.ipynb`. You've completed it on your computer (maybe in Google Colab or Jupyter).

**Option A: Copy the file using File Explorer / Finder**

1. Open your file explorer
2. Navigate to `ai-adventure/submissions/Rocky_Ganji_B230001/`
3. Copy-paste your `python_fundamentals.ipynb` file into this folder

**Option B: Copy using the terminal**

If your notebook is on the Desktop:

```bash
# Windows (Git Bash)
cp ~/Desktop/python_fundamentals.ipynb .

# Mac / Linux
cp ~/Desktop/python_fundamentals.ipynb .
```

> 💡 The `.` at the end means "current folder" — which should be your personal folder inside submissions.

**Option C: If you downloaded it from Google Colab**

1. In Google Colab: File → Download → Download `.ipynb`
2. Find the downloaded file (usually in your `Downloads` folder)
3. Copy it to your folder:

```bash
cp ~/Downloads/python_fundamentals.ipynb .
```

### Verify the file is there:

```bash
ls
```

You should see:
```
python_fundamentals.ipynb
```

---

## ✅ Step 6: Stage Your Changes

Now Git needs to know about your new files. First, go back to the **root** of the project:

```bash
cd ../../..
```

> 💡 **Not sure if you're in the right place?** Run `ls` — you should see `README.md`, `notes/`, `submissions/`, and `CONTRIBUTING.md`.

Check what Git sees:

```bash
git status
```

You'll see something like:
```
Untracked files:
    submissions/Rocky_Ganji_B230001/python_fundamentals.ipynb
```

Now stage (prepare) your files for commit:

```bash
git add submissions/Rocky_Ganji_B230001/
```

> 💡 **Why not `git add .`?** Using the specific path is safer — it ensures you're only adding YOUR files and not accidentally touching anything else.

---

## 💾 Step 7: Commit Your Changes

A **commit** is like saving a checkpoint with a message describing what you did.

```bash
git commit -m "Add python_fundamentals assignment - Rocky Kumar B230001"
```

### Commit Message Rules:

✅ **Good commit messages:**
```
Add python_fundamentals assignment - Rocky Kumar B230001
Submit assignment 2 - Priya Sharma B230045
Add LLM basics notes - Mohammed Ali B230112
```

❌ **Bad commit messages:**
```
update                    ← too vague
asdfgh                    ← meaningless
done                      ← what is done?
added file                ← which file? who are you?
```

---

## 🚀 Step 8: Push to Your Fork

**Pushing** uploads your local commits to your GitHub fork:

```bash
git push origin main
```

> If asked for credentials, enter your GitHub username and **Personal Access Token** (not your password).

### How to create a Personal Access Token (if needed):

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click **"Generate new token (classic)"**
3. Give it a name like `ai-adventure`
4. Select the **`repo`** scope (checkbox)
5. Click **"Generate token"**
6. **Copy the token immediately** (you won't see it again!)
7. Use this token as your password when Git asks

---

## 🔀 Step 9: Create a Pull Request (PR)

A **Pull Request** is how you say: *"Hey, I've done my work — please review and merge it into the main repo."*

### How to create a PR:

1. Go to **your forked repo** on GitHub: `github.com/YOUR_USERNAME/ai-adventure`

2. You'll see a banner that says:
   > **"This branch is 1 commit ahead of infinitethoughts7:main"**

3. Click **"Contribute"** → **"Open pull request"**

4. You'll see a comparison page. Fill in:

   **Title:**
   ```
   Submission: Rocky Kumar B230001 - python_fundamentals
   ```

   **Description (body):**
   ```
   - Assignment: python_fundamentals.ipynb
   - Name: Rocky Kumar
   - Roll Number: B230001
   - Status: Completed
   ```

5. Click **"Create pull request"**

6. Done! 🎉 Now wait for the trainer to review and merge your PR.

### What happens next?

- The trainer will **review** your submission
- If everything looks good → **Merged** ✅
- If changes are needed → You'll see **comments** on your PR. Fix them and push again (the PR updates automatically).

---

## 🔄 Submitting Future Assignments (After Your First Time)

You've already forked and cloned — so for the next assignment, the process is shorter.

### First: Sync your fork with the latest changes

```bash
cd ai-adventure
```

```bash
git pull upstream main
```

> ⚠️ If you haven't set `upstream` yet, run this **once**:
> ```bash
> git remote add upstream https://github.com/infinitethoughts7/ai-adventure.git
> ```

### Then: Add your new assignment

```bash
cd submissions/Rocky_Ganji_B230001
```

Copy your new assignment file here (e.g., `llm_basics.ipynb`), then:

```bash
cd ../../..
git add submissions/Rocky_Ganji_B230001/
git commit -m "Add llm_basics assignment - Rocky Kumar B230001"
git push origin main
```

Then go to GitHub and **create a new Pull Request** (same steps as Step 9).

---

## 📁 What Your Folder Should Look Like Over Time

As you submit more assignments, your folder grows:

```
submissions/
└── Rocky_Ganji_B230001/
    ├── python_fundamentals.ipynb      ← Assignment 1
    ├── python_oop.ipynb               ← Assignment 2
    ├── llm_basics.ipynb               ← Assignment 3
    ├── langchain_intro.ipynb          ← Assignment 4
    └── ai_agent_project.ipynb         ← Final Project
```

> 🎯 This becomes your **portfolio**. Keep it clean and well-organized!

---

## 🔄 Quick Reference — Git Commands Cheat Sheet

| Command | What It Does |
|---------|-------------|
| `git clone <url>` | Download a repository to your computer |
| `cd <folder>` | Navigate into a folder |
| `mkdir <name>` | Create a new folder |
| `ls` | List files in current folder |
| `pwd` | Show your current location (Mac/Linux) |
| `cp <source> <destination>` | Copy a file |
| `git status` | Check what files have changed |
| `git add <path>` | Stage specific files for commit |
| `git commit -m "message"` | Save your changes with a description |
| `git push origin main` | Upload your commits to GitHub |
| `git pull upstream main` | Get latest changes from the original repo |
| `git remote -v` | See your connected remote repositories |

---

## 🆘 Common Errors & Fixes

### ❌ "fatal: not a git repository"
**You're not inside the project folder.** Run:
```bash
cd ai-adventure
```

### ❌ "error: failed to push some refs"
**Your fork is behind the original repo.** Run:
```bash
git pull upstream main
```
Then push again.

### ❌ "Permission denied" or "Authentication failed"
**You need a Personal Access Token.** See Step 8 for how to create one.

### ❌ "fatal: remote origin already exists"
**This is fine** — it means you've already set it up. Continue with the next step.

### ❌ "nothing to commit, working tree clean"
**You haven't added any new files**, or you already committed. Check with `git status`.

---

## 🧭 Where to Find Things on GitHub

| What You Need | Where to Find It |
|--------------|-----------------|
| The original repo | [github.com/infinitethoughts7/ai-adventure](https://github.com/infinitethoughts7/ai-adventure) |
| Your forked repo | `github.com/YOUR_USERNAME/ai-adventure` |
| Learning materials & books | `notes/` folder in the repo |
| Other students' submissions | `submissions/` folder in the repo |
| Your Pull Requests | Go to the original repo → **"Pull requests"** tab |
| Issues / Questions | Go to the original repo → **"Issues"** tab |
| Star the repo ⭐ | Click the **"Star"** button at the top-right of the repo page |

---

## 📋 Submission Checklist

Before creating a Pull Request, verify:

- [ ] My folder is inside `submissions/` with the correct naming: `FirstName_LastName_RollNumber`
- [ ] My assignment file (`.ipynb`) is inside my folder
- [ ] I have NOT modified any files outside my folder
- [ ] My commit message includes my name and roll number
- [ ] I created the PR against the original repo (not my own fork)

---

<p align="center">
  <b>Still stuck? Ask in the group chat or raise your hand in class. No question is silly! 🙋</b>
</p>
