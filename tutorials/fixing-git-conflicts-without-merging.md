# Fixing git conflicts without merging

1. Make sure your master branch is in the last version

```sh
git checkout master
git pull
```

2. Go to the branch with conflicts

```sh
git checkout feature/my-branch
```

3. Solve conflicts locally

```sh
git rebase origin/master
```

4. Commit changes

```sh
git add .
git commit -m "chore(*): fix merge conflicts"
```

5. Push the solved info to repository

```sh
git push -f origin HEAD:feature/my-branch
```
