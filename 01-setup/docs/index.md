---
layout: default
title: "01 -- Setup and Installation"
---

# Setup and Installation

Before we write any code, we need to get your tools set up. By the end of this lesson, you'll have Python, a code editor, and Jupyter Notebook running on your laptop.

Everyone will use the same setup so we can troubleshoot together and stay on the same page.

---

## What We're Installing

| Tool | What It Does |
|------|-------------|
| **Python** | The programming language |
| **VS Code** or **Antigravity** | Your code editor (pick one -- these are the only two options) |
| **Jupyter Notebook** | An interactive environment for writing and running code in cells (required for HPC later) |

---

## Step 1: Install Python

### Mac

Python 3 may already be installed. Open **Terminal** (search for it in Spotlight) and check:

```bash
python3 --version
```

If you see `Python 3.x.x`, you're good -- skip to Step 2.

If not, install it:

1. Go to [python.org/downloads](https://www.python.org/downloads/)
2. Download the latest Python 3 installer for macOS
3. Open the `.pkg` file and follow the prompts
4. When it finishes, close and reopen Terminal, then verify:

```bash
python3 --version
```

### Windows

1. Go to [python.org/downloads](https://www.python.org/downloads/)
2. Download the latest Python 3 installer for Windows
3. **Important:** On the first screen of the installer, check the box that says **"Add python.exe to PATH"** before clicking Install
4. Click **Install Now** and let it finish
5. Open **Command Prompt** (search for "cmd" in the Start menu) and verify:

```bash
python --version
```

> **Windows note:** On Windows, the command is `python`. On Mac, it's `python3`. This is normal.

---

## Step 2: Install Your Code Editor

You must use one of these two editors. Pick one and stick with it for the bootcamp.

### Option A: VS Code (recommended)

1. Go to [code.visualstudio.com](https://code.visualstudio.com/)
2. Download for your operating system and install
3. Open VS Code
4. Install the **Python extension:**
   - Click the Extensions icon in the left sidebar (it looks like four squares)
   - Search for "Python"
   - Install the one by Microsoft (it should be the top result)
5. Install the **Jupyter extension:**
   - Same process -- search for "Jupyter" and install the one by Microsoft

### Option B: Antigravity

1. Go to [antigravity.app](https://antigravity.app/)
2. Download for your operating system and install
3. Open the app -- Python and Jupyter support are built in

---

## Step 3: Clone the Course Repo

Open your terminal (Mac: Terminal, Windows: Command Prompt) and run:

```bash
git clone https://github.com/morehouse-supercomputing/python-bootcamp.git
cd python-bootcamp
```

This downloads all the course notebooks to your laptop. Before each class, pull the latest updates:

```bash
git pull
```

> **Don't have Git?** Download it from [git-scm.com](https://git-scm.com/downloads). We'll cover Git in detail in [Lesson 05](../05-git-and-github/). If you can't install it right now, download the repo as a ZIP from GitHub instead.

---

## Step 4: Set Up Your Virtual Environment

A **virtual environment** (venv) is an isolated Python setup for a specific project. It keeps the libraries you install for this bootcamp separate from everything else on your laptop. This prevents version conflicts and keeps things clean.

### Mac

```bash
python3 -m venv venv
source venv/bin/activate
```

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

When the venv is active, you'll see `(venv)` at the beginning of your terminal prompt. That means it's working.

> **Every time you open a new terminal to work on bootcamp materials, you need to activate the venv again.** Just `cd` into the `python-bootcamp` folder and run the activate command.

### What's a `requirements.txt`?

The repo includes a file called `requirements.txt` that lists every library the bootcamp uses. Instead of installing things one at a time, you install them all at once:

```bash
pip install -r requirements.txt
```

This installs:

| Library | What It's For | When We Use It |
|---------|--------------|----------------|
| **jupyter** | Interactive notebooks (required for TACC later) | Every lesson |
| **numpy** | Arrays and math operations | Week 1 |
| **pandas** | Working with data tables and CSVs | Week 2 |
| **matplotlib** | Charts and graphs | Week 2 |
| **seaborn** | Statistical visualizations | Week 2 |
| **requests** | Calling APIs and fetching data from the web | Week 2 |

Verify everything installed:

```bash
jupyter notebook --version
python -c "import numpy, pandas, matplotlib, seaborn, requests; print('All libraries installed!')"
```

> **If `pip` is not recognized (Windows):** Close Command Prompt, reopen it, and try again. If it still doesn't work, Python wasn't added to your PATH. Reinstall Python and check the "Add python.exe to PATH" box.

> **If `pip` or `python3` gives errors (Mac):** Try `python3 -m pip install -r requirements.txt` instead.

---

## Step 5: Open Your First Notebook

### In VS Code

1. Open VS Code
2. Click **File > Open Folder** and select the `python-bootcamp` folder
3. In the file explorer on the left, navigate to `01-setup/notebook.ipynb`
4. Click it to open -- VS Code will render it as a notebook
5. Click the **Run** button on the first cell (or press **Shift + Enter**)
6. If prompted to select a kernel, choose **Python 3**

### In Antigravity

1. Open Antigravity
2. Click **File > Open** and navigate to `python-bootcamp/01-setup/notebook.ipynb`
3. Click the **Run** button on the first cell

### From the Command Line (either OS)

You can also launch Jupyter directly:

```bash
cd python-bootcamp/01-setup
jupyter notebook
```

This opens your browser to a local Jupyter server where you can click `notebook.ipynb` to open it.

---

## How Notebooks Work

A Jupyter notebook is made up of **cells**. There are two types:

| Cell Type | What It's For |
|-----------|--------------|
| **Code** | Write and run Python code |
| **Markdown** | Write text, headings, notes |

Key shortcuts:

| Shortcut | What It Does |
|----------|-------------|
| **Shift + Enter** | Run the current cell and move to the next |
| **Ctrl + Enter** | Run the current cell and stay on it |
| **Esc, then A** | Insert a cell above |
| **Esc, then B** | Insert a cell below |
| **Esc, then M** | Convert cell to Markdown |
| **Esc, then Y** | Convert cell to Code |

---

## Troubleshooting

### "python" / "python3" is not recognized

**Windows:** Python wasn't added to your PATH during installation. Reinstall Python and check the "Add python.exe to PATH" box on the first screen.

**Mac:** Try `python3` instead of `python`. If that doesn't work, reinstall from [python.org](https://www.python.org/downloads/).

### "pip" / "pip3" is not recognized

**Windows:** Same fix as above -- reinstall Python with the PATH checkbox.

**Mac:** Use `python3 -m pip install jupyter` instead of `pip3 install jupyter`.

### Jupyter opens in the browser but shows no files

You launched `jupyter notebook` from the wrong directory. Navigate to your project folder first:

```bash
cd python-bootcamp/01-setup
jupyter notebook
```

### VS Code says "No kernel found" or "Select a kernel"

Click the kernel selector in the top right of the notebook and choose **Python 3**. If Python 3 doesn't appear, make sure you installed the Python and Jupyter extensions.

### The notebook runs but nothing happens

Make sure you're clicking inside a **code cell** (it should have a play button or say `In [ ]` next to it). Markdown cells don't produce output.

---

## What's Next

Now that your environment is ready, we'll start writing Python: [Variables and Types](../02-variables-and-types/).

---

[Back to home](../)
