# 👋 GWC Guestbook

Welcome! In this activity you'll add yourself to our guestbook using **Git, GitHub, and the terminal**, following the same workflow developers use every day.

**Your goal:** add a file about yourself to the `attendees/` folder and get it merged into this repo.

```
fork → clone → branch → edit → add → commit → push → pull request
```

> 💡 **Windows users:** do everything in **Git Bash**, not PowerShell.
> 
> 💡 **Mac users:** use **Terminal**.
> 
> 💡 Replace anything in `<angle brackets>` (and `first-last`) with your own info. Don't type the brackets!

---

## 0. Setup check

Make sure Git is installed:

```bash
git --version
```

You should see a version number. Then tell Git who you are (use the email from your GitHub account):

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

---

## 1. Fork this repo

Click the **Fork** button in the top-right corner of this page, then **Create fork**.

You now have your own copy of this repo on your GitHub account.

---

## 2. Find your way around the terminal

```bash
pwd          # where am I?
ls           # what's in this folder?
cd Desktop   # move into your Desktop folder
```

---

## 3. Clone your fork and move into it

On **your fork** (check that the URL has *your* username), click the green **Code** button and copy the URL. Then:

```bash
git clone <your-fork-url>
cd gwc-guestbook
ls
```

---

## 4. Create a new branch

```bash
git checkout -b add-first-last
# example: git checkout -b add-alexis-cruz
git branch
```

The `*` shows which branch you're on.

---

## 5. Edit files ✏️

Move into the `attendees` folder and create your file:

```bash
cd attendees
touch first-last.md
echo "Hi! I'm <name>, and my favorite food is <answer>" >> first-last.md
cat first-last.md
```

Check out `alexis-cruz.md` if you want an example!

---

## 6. Stage your changes

```bash
git status
```

Your file shows up in **red**, which means it isn't staged yet.

```bash
git add first-last.md
git status
```

Now it's **green**, so it's staged and ready to commit.

---

## 7. Commit your changes

```bash
git commit -m "Add <first-last> to guestbook"
git log --oneline
```

You should see your commit at the top of the history.

---

## 8. Push to GitHub

```bash
git push -u origin add-first-last
```
This is your first push, so you may be asked to sign in. **Windows:** follow the browser pop-up. **Mac:** see [Troubleshooting](#-troubleshooting).

---

## 9. Open a pull request

1. Go to **your fork** on GitHub.
2. Click the **Compare & pull request** button that appears.
3. Click **Create pull request**.

---

## 🆘 Troubleshooting

**"command not found: git"**
Git isn't installed yet, or your terminal was opened before the install finished. Close the terminal, open a new one, and try again. On Windows, make sure you're in **Git Bash**.

**Stuck in a weird text editor after `git commit`?**
You forgot the `-m`. Press `Esc`, type `:wq`, and hit **Enter**.

**"Permission denied" or "403" when pushing**
You probably cloned the original repo instead of your fork. Check with:
```bash
git remote -v
```
If the URL doesn't have your username, go back to step 3 and clone your fork.

**Push asks for a password and rejects it (Mac)**
GitHub doesn't accept your account password in the terminal. Use a personal access token instead:

1. On GitHub, click your profile picture → **Settings**
2. Scroll down and click **Developer settings** (bottom of the left sidebar)
3. Click **Personal access tokens** → **Tokens (classic)** → **Generate new token (classic)**
4. Give it a name (e.g. `gwc workshop`), check the **repo** box, and click **Generate token**
5. **Copy the token now.** GitHub only shows it once!
6. Run your push again:
   ```bash
   git push -u origin add-first-last
   ```
7. When asked for your **username**, type your GitHub username
8. When asked for your **password**, paste your token

> 💡 Nothing will appear on screen when you paste the token. That's normal! Just press **Enter**.

Your Mac will remember the token, so you won't need to do this again.

**Lost in your folders?**
```bash
pwd     # see where you are
cd ..   # go up one folder
ls      # see what's here
```
