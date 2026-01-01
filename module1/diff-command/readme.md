# Understanding `diff` and `patch` Commands

## `diff` Command

The `diff` command compares files line by line and shows the differences between them.

**Basic Usage:**
```sh
diff main.py main_fixed.py
```
This outputs the lines that differ between `main.py` and `main_fixed.py`.

**Common Options:**
- `-u`: Unified format, easier to read and used for patches.
- `-c`: Context format, shows surrounding lines for context.

**Example:**
```sh
diff main.py main_fixed.py > changes.diff
```
Or
```sh
diff -u old.txt new.txt > changes.patch
```


This creates a patch file with the differences.

---

## `patch` Command

The `patch` command applies changes to files using a patch file (usually created by `diff`).

**Basic Usage:**
```sh
patch main.py changes.diff 
```
Or
```sh
patch < changes.patch
```
This updates the original files according to the instructions in `changes.patch`.

**Workflow Example:**
1. Make changes to a file.
2. Run `diff -u original.txt modified.txt > update.patch`.
3. Share `update.patch` with others.
4. Others run `patch < update.patch` to apply the changes.

---

## Summary

- Use `diff` to find differences and create patch files.
- Use `patch` to apply those differences to files.
- This workflow is useful for code reviews, collaboration, and version control.
