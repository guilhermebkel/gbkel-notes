# Squashing a commit

Sometimes you will want to merge some commits into a single commit, we call it a commit squash.

**1. Give a look at the last repository commits:**
```sh
git l
```

**2. Select the first commit before the commit you want to start squashing:**

Per example, in case I have the following commits:
```
7d62c4c (HEAD -> feat/adonis-debug, origin/feat/adonis-debug) chore(debug): change debug config name - Guilherme Mota, 8 minutes ago

8a96dbc chore(debug): add correct remote root path - Guilherme Mota, 8 minutes ago

383f994 style(vscode): use spaces on indentation - Guilherme Mota, 3 days ago

17edbd8 chore(debug): keep debug config file inside repository - Guilherme Mota, 3 days ago

cc58173 docs(debug): update debug config on readme - Guilherme Mota, 3 days ago

9b71f94 chore(debug): add tutorial to setup debug with vscode - Guilherme Mota, 3 days ago

1eb26ec chore(package): add flag to use node js debugger - Guilherme Mota, 4 days ago

85ea258 (origin/develop, origin/HEAD, develop) feat(core): add subscriptions - Saulo Soares de Toledo, 8 days ago
```

And I want to merge from **7d62c4c** to **1eb26ec**, I need to select the commit **85ea258**.

**3. Now use a git rebase command using the commit hash you selected in the last step:**

```
git rebase -i 85ea258
```

**4. Now change the pick prefix for squash in every commit you want to merge**.

Obs:

- Make sure you let the first (up-down) commit with **pick** prefix in order to merge all the commits below it with itself.

**5. Now, after saving the file, it will appears a new file that you can clear all content and add a new commit name for this merged commits.**

**6. After selecting a new commit name, run the following command in order to update the tree on the repository:**

```
git push -f
```