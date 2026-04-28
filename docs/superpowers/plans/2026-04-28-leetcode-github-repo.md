# LeetCode GitHub Repo Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a public GitHub repo with difficulty-based folder structure and migrate existing Python solutions into it.

**Architecture:** Flat difficulty folders (`easy/`, `medium/`, `hard/`) at the repo root. Files named `{number}_{snake_case_title}.py`. A README table tracks all solved problems.

**Tech Stack:** Python 3, Git, GitHub CLI (`gh`)

---

### Task 1: Initialize the repo and folder structure

**Files:**
- Create: `easy/`
- Create: `medium/`
- Create: `hard/`
- Create: `README.md`
- Create: `.gitignore`

- [ ] **Step 1: Initialize git repo**

```bash
cd /Users/guidofajardo/Desktop/LeetCode
git init
```

Expected output: `Initialized empty Git repository in .../LeetCode/.git/`

- [ ] **Step 2: Create difficulty folders with a .gitkeep so they're tracked**

```bash
mkdir -p easy medium hard
touch easy/.gitkeep medium/.gitkeep hard/.gitkeep
```

- [ ] **Step 3: Create .gitignore**

Create `/Users/guidofajardo/Desktop/LeetCode/.gitignore`:

```
__pycache__/
*.pyc
.DS_Store
```

- [ ] **Step 4: Create README.md**

Create `/Users/guidofajardo/Desktop/LeetCode/README.md`:

```markdown
# LeetCode Solutions

Python 3 solutions to LeetCode problems, organized by difficulty.

## Problems

| # | Problem | Difficulty | Link |
|---|---------|------------|------|
| 1480 | Running Sum of 1d Array | Easy | [LeetCode](https://leetcode.com/problems/running-sum-of-1d-array/) |
| 2235 | Add Two Integers | Easy | [LeetCode](https://leetcode.com/problems/add-two-integers/) |
```

- [ ] **Step 5: Commit**

```bash
cd /Users/guidofajardo/Desktop/LeetCode
git add README.md .gitignore easy/.gitkeep medium/.gitkeep hard/.gitkeep
git commit -m "chore: initialize repo with difficulty folder structure"
```

---

### Task 2: Migrate existing solutions into easy/

**Files:**
- Create: `easy/1480_running_sum_of_1d_array.py`
- Create: `easy/2235_add_two_integers.py`
- Delete: `Python3/1480_Running_Sum_of_1d_Array`
- Delete: `Python3/2235_Add_Two_Integers.py`

- [ ] **Step 1: Create easy/1480_running_sum_of_1d_array.py**

```python
from typing import List


class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        for i in range(1, len(nums)):
            nums[i] += nums[i - 1]
        return nums
```

- [ ] **Step 2: Create easy/2235_add_two_integers.py**

```python
class Solution:
    def sum(self, num1: int, num2: int) -> int:
        return num1 + num2
```

- [ ] **Step 3: Remove the old Python3/ folder**

```bash
rm -rf /Users/guidofajardo/Desktop/LeetCode/Python3
```

- [ ] **Step 4: Commit migration**

```bash
cd /Users/guidofajardo/Desktop/LeetCode
git add easy/1480_running_sum_of_1d_array.py easy/2235_add_two_integers.py
git rm -r Python3/
git commit -m "feat: migrate existing solutions to easy/ folder"
```

---

### Task 3: Create GitHub repo and push

**Files:** No file changes — GitHub setup only.

- [ ] **Step 1: Create public GitHub repo via CLI**

```bash
gh repo create leetcode --public --description "LeetCode solutions in Python 3" --source /Users/guidofajardo/Desktop/LeetCode --remote origin --push
```

Expected: repo created at `https://github.com/<your-username>/leetcode` and all commits pushed.

- [ ] **Step 2: Verify on GitHub**

Open the repo URL printed by the previous command and confirm:
- `easy/`, `medium/`, `hard/` folders are visible
- `README.md` renders the problem table correctly
- Both solution files are inside `easy/`
