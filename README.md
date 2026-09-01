# LabVault 🔐

> **The one vault that hoards every lab program you've ever written, so you never have to dig through old folders again.**

A sleek, self-updating vault for your lab programs — pulled live from GitHub, organized week by week, ready whenever you need to revisit them.

---

## What is LabVault?

LabVault is a beautiful web app that turns your GitHub lab repository into an organized, searchable code vault. Instead of hunting through folders or scrolling through commits to find that one sorting algorithm you wrote, everything lives in one place — organized by week, instantly searchable, and automatically updated as you push new code.

**Perfect for:**
- 📚 Students managing multiple lab courses
- 🔍 Quick reference during exams or debugging
- 📈 Tracking your progress week by week
- 🎓 Building a clean portfolio from your work

---

## How It Works (Simple Version)

Think of LabVault like a smart filing cabinet that watches your GitHub repo:

1. **You push code to GitHub** (like you normally do)
2. **LabVault checks your repo** automatically
3. **Your programs appear organized by week** — no manual updates needed
4. **Click any file to see syntax-highlighted code** in a clean modal
5. **Copy code with one click** for studying or reference

That's it. No configuration, no build steps, no backend server. Just open the app, and it does the work.

---

## Tech Stack (Explained)

This project is built with **minimal, elegant dependencies**:

| Tech | What It Does | Why We Use It |
|------|-------------|---------------|
| **HTML/CSS/JavaScript** | Core app logic, styling, interactions | Pure, no build step needed — the app is one file |
| **GitHub REST API** | Fetches your repo structure and file contents | Free, public, no authentication required for public repos |
| **highlight.js** | Syntax highlighting for code | Makes C, C++, Python code readable and colorful |
| **Framer Motion (CSS animations)** | Smooth transitions and entrance effects | Glass aesthetic with glassmorphism + subtle animations |
| **Static hosting** | Vercel, Netlify, or GitHub Pages | No server-side code needed — it's all client-side |

**That's it.** No React, no build tools, no node_modules. Just a single `index.html` file that you can:
- Drop on Vercel/Netlify
- Host on GitHub Pages
- Open locally in your browser
- Send to friends

---

## Getting Started

### Option 1: Use It Right Now (Easiest)

Just open the app directly or deploy it:

1. **Download `labvault.html`** from this repo
2. **Open it in any browser** — that's it
3. The app is already configured to pull from `akshat-2337/data-structures-lab-code`

### Option 2: Deploy It (Free Hosting)

**On Vercel:**
1. Create a `vercel.json` file with:
   ```json
   {
     "public": true
   }
   ```
2. Deploy the `labvault.html` file to Vercel
3. Share the link with your friends

**On Netlify:**
1. Drag and drop `labvault.html` into Netlify
2. Get a live URL instantly
3. Done

**On GitHub Pages:**
1. Create a repo called `labvault`
2. Add `labvault.html` as `index.html`
3. Enable GitHub Pages in repo settings
4. Your app is live at `yourusername.github.io/labvault`

### Option 3: Customize for Your Repo

Want to point LabVault at *your* data structures repo instead? Edit this one line in the HTML:

```javascript
const CONFIG = {
  owner: 'YOUR_GITHUB_USERNAME',     // Change this
  repo: 'YOUR_REPO_NAME',             // And this
  maxPlaceholderWeeks: 3,
  apiBase: 'https://api.github.com/repos',
  cachePrefix: 'labvault_'
};
```

Save it, refresh, and it's pulling from your repo.

---

## How to Use It

### As a Student

**Scenario 1: You just finished Week 3 labs**
- Push your `week3` folder to GitHub
- Refresh LabVault
- Week 3 appears automatically with all your programs listed
- Click any file to read your code with syntax highlighting
- Copy any snippet for study notes

**Scenario 2: It's exam prep time**
- Open LabVault
- Expand Week 1 → find that linked list implementation you wrote
- Click it → read your code, understand your logic, copy for notes
- Takes 10 seconds instead of 5 minutes of folder hunting

**Scenario 3: You're debugging a pointer issue**
- Expand the week where you worked on pointers
- Scan all your files at once
- Click the one you need → full code with syntax highlighting
- Copy it to your IDE if needed

### As a Teacher/Mentor

LabVault works great for:
- 📋 **Code review** — organized, easy navigation
- 📊 **Progress tracking** — see at a glance what students completed each week
- 🎁 **Portfolio building** — show this to recruiters as proof of coursework

---

## Features That Make It Special

✨ **Automatic Updates**
- Push new code to GitHub → it appears on LabVault automatically
- No redeploys, no rebuilds, no code changes needed

🔐 **Dark Glassmorphism Design**
- Beautiful soft-black background with frosted glass panels
- Blue accents for active elements, orange for coming soon
- Neon highlights for interactions
- Looks like a hacker's terminal, feels like a vault

⚡ **Blazing Fast**
- Single HTML file, no build process
- Cached locally in your browser for instant revisits
- Syntax highlighting runs in your browser (not on a server)

🎯 **Clean & Organized**
- Files grouped by week automatically
- One-click access to any program
- No clutter, no ads, no tracking

♿ **Accessible**
- Keyboard navigation (Tab through everything)
- Focus traps in modals (can't accidentally tab outside)
- Respects your reduced-motion preferences
- Clear focus indicators
- Works on mobile, tablet, desktop

---

## The Week Folder Structure

LabVault expects your GitHub repo to look like this:

```
data-structures-lab-code/
├── week1/
│   ├── stack.c
│   ├── queue.c
│   └── linked_list.c
├── week2/
│   ├── binary_search.c
│   ├── sorting.c
│   └── recursion.c
├── week3/
│   └── graphs.c
└── README.md
```

**LabVault automatically:**
- Finds all `weekN` folders (week1, week2, week3, etc.)
- Shows them in order
- Lists files inside each week
- Shows "Coming Soon" for weeks you haven't pushed yet
- Updates when you add new weeks or files

---

## Real-World Example

Let's say you're in a Data Structures course with 8 weeks of labs:

**Week 1:** You push `week1/` with 3 C programs
- LabVault shows Week 1 active with 3 files
- Weeks 2-3 show as "Coming Soon"

**Week 2:** You finish and push `week2/` with 4 programs
- Refresh LabVault
- Week 2 now shows as active with your 4 files
- Week 3 still says "Coming Soon"

**Mid-semester review:** You need to review your linked list code
- Open LabVault
- Click Week 1 → expand
- Click `linked_list.c`
- Syntax-highlighted code appears in a modal
- Copy it to your notes or IDE

**Exam prep:** You're reviewing pointer arithmetic
- Open LabVault → search visually through all your weeks
- Find the pointer-heavy programs
- Review them all in one place
- No folder switching, no terminal commands

---

## Benefits for Students

| Benefit | Why It Matters |
|---------|----------------|
| **Organized Portfolio** | Shows recruiters you can write clean, organized code across multiple concepts |
| **Revision Tool** | Perfect for exam prep — all your code in one searchable place |
| **Learning Reference** | Review old code to see how you solved similar problems |
| **Quick Access** | Instead of `cd ~/Desktop/sem4/dsa/week2/...` just open LabVault |
| **Version Control** | GitHub is your source of truth; this just displays it beautifully |
| **Zero Maintenance** | Push code → it appears. That's it. |

---

## Technologies Explained Simply

**GitHub API**
- Your repo is public → GitHub lets anyone request its contents
- LabVault asks: "Hey GitHub, what's in `akshat-2337/data-structures-lab-code`?"
- GitHub responds with a list of weeks and files
- No login needed, free, instant

**Syntax Highlighting**
- highlight.js: a free library that colors code
- C looks blue, strings look green, comments look grey
- Makes reading code 10x easier than plain text

**Glassmorphism**
- A design trend: frosted glass effect with blur and transparency
- CSS `backdrop-filter: blur()` creates the effect
- It's not just pretty — it also makes code scannable

**sessionStorage Caching**
- Your browser remembers what we fetched from GitHub
- Refresh the page → instant load (no API call needed)
- Push new code → hit the Refresh button to clear cache
- Saves bandwidth and keeps you under GitHub's rate limit

---

## FAQ

**Q: Do I need to sign up or log in?**
A: Nope. Open the app, point it at your public GitHub repo, done.

**Q: What if my repo is private?**
A: Add a GitHub personal access token to the config. (Instructions in code comments.)

**Q: Can I edit code in LabVault?**
A: No, it's read-only. Edit your code in your IDE, push to GitHub, LabVault displays it.

**Q: What if I hit GitHub's rate limit?**
A: You get a friendly error message with a retry button. Limits reset every hour. Use the Refresh button sparingly to stay under the 60 requests/hour limit.

**Q: Can I use this for other subjects?**
A: Yes! Just change the `owner` and `repo` in the config. Works for any GitHub repo with week-organized code.

**Q: Is my code safe?**
A: Totally. LabVault doesn't store or process your code — it only reads from your public GitHub repo. No data is sent anywhere except to GitHub (which you control).

---

## Customization Ideas

- **Change colors:** Edit the CSS variables at the top (`--blue`, `--orange`, `--neon`)
- **Add more subjects:** Duplicate the config and run multiple instances (one for DS, one for Algorithms, etc.)
- **Change max placeholder weeks:** If your course is 12 weeks, change `maxPlaceholderWeeks: 12`
- **Adjust animations:** Modify the `@keyframes` and transition timings

---

## What Happens Behind the Scenes

1. **Page loads** → LabVault fetches your repo's root folder from GitHub
2. **You see weeks:** Weeks that exist show as active, future weeks show as "Coming Soon"
3. **You click a week** → LabVault fetches the list of files in that week (cached for speed)
4. **You click a file** → LabVault downloads that file's content and highlights the syntax
5. **You hit Refresh** → Cache clears, everything re-fetches fresh

No magic, no backend, no complexity.

---

## Built With Love ❤️

- **Pure JavaScript** (no frameworks needed)
- **GitHub REST API** (free tier works great)
- **highlight.js** (syntax highlighting)
- **CSS animations** (smooth, delightful interactions)
- **A pinch of glassmorphism** (makes it look cool)

**Proudly engineered with Claude** — an AI assistant that helped design and build this from scratch.

---

## License

MIT — use it, modify it, share it, build on it.

---

## Next Steps

1. **Download or deploy** `labvault.html`
2. **Configure it** for your GitHub repo (or use the default)
3. **Push your labs** to GitHub
4. **Open LabVault** and watch your vault fill up
5. **Share it** with classmates, mentors, or future employers

---

**Questions? Ideas? Issues?**

Open an issue on the [GitHub repo](https://github.com/akshat-2337/data-structures-lab-code) or fork it to customize further.

Happy vaulting! 🔐✨
