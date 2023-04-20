# Creating a Private Fork on Github

***Obs.:*** Suppose we are using the repository **start/yellow** as an example.

1. Create a bare clone of the repository. (This is temporary and will be removed so just do it wherever.)
```bash
git clone --bare git@github.com:start/yellow.git
```

2. [Create a new private repository on Github](https://help.github.com/articles/creating-a-new-repository/) and name it `yellow`.

3. Mirror-push your bare clone to your new `start/yellow` repository.
> Replace `<your_username>` with your actual Github username in the url below.

```bash
cd start/yellow.git
git push --mirror git@github.com:<your_username>/start/yellow.git
```

4. Remove the temporary local repository you created in step 1.
```bash
cd ..
rm -rf start/yellow.git
```
	
5. You can now clone your `start/yellow` repository on your machine.
```bash
git clone git@github.com:<your_username>/start/yellow.git
```
	
6. If you want, add the original repo as remote to fetch (potential) future changes. Make sure you also disable push on the remote (as you are not allowed to push to it anyway).

```bash
git remote add upstream git@github.com:start/yellow.git
git remote set-url --push upstream DISABLE
```

You can list all your remotes with `git remote -v`. You should see:

```
origin	git@github.com:<your_username>/start/yellow.git (fetch)
origin	git@github.com:<your_username>/start/yellow.git (push)
upstream	git@github.com:start/yellow.git (fetch)
upstream	DISABLE (push)
```

> When you push, do so on `origin` with `git push origin`.
>
> When you want to pull changes from `upstream` you can just fetch the remote and rebase on top of your work.

```bash
git fetch upstream
git rebase upstream/master
```

And solve the conflicts if any

### Bibliographic References:

> https://help.github.com/articles/duplicating-a-repository
> https://gist.github.com/0xjac/85097472043b697ab57ba1b1c7530274