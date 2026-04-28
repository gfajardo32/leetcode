# LeetCode GitHub Repo Design

**Date:** 2026-04-28

## Goal

Create a public GitHub repository to organize LeetCode solutions, starting with Python only, organized by difficulty.

## Structure

```
leetcode/
  easy/
    1480_running_sum_of_1d_array.py
    2235_add_two_integers.py
  medium/
  hard/
  README.md
```

## Conventions

- **Language:** Python 3 only (for now)
- **File naming:** `{number}_{snake_case_title}.py`
- **Difficulty folders:** `easy/`, `medium/`, `hard/` at the repo root

## README

A table with columns: `#`, `Problem`, `Difficulty`, `LeetCode Link`.  
One row per solved problem, manually updated when a new solution is added.

## Migration

Move existing files from `Python3/` into the appropriate difficulty folder:
- `2235_Add_Two_Integers.py` → `easy/2235_add_two_integers.py`
- `1480_Running_Sum_of_1d_Array` → `easy/1480_running_sum_of_1d_array.py`

## Out of Scope

- Multi-language support (deferred)
- Topic/tag subfolders (deferred)
- Automated README generation (deferred)
