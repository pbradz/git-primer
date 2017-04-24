# git-primer

## Get Started (First Time)

```bash
git config --global user.name "Jay Doe"
git config --global user.email jdoe@example.org
```

## Create a GitHub Repo
Visit the [Gladstone Institutes group](https://github.com/gladstone-institutes) and click the green "New" button. Fill out the forms, and you'll get a page with instructions on how to create a new repository on the command line, push an existing repository from the command line or import code from a non-git repository.

## Clone a GitHub Repo
Visit the desired repository, e.g., [git-primer](https://github.com/gladstone-institutes/git-primer), and click the green "Clone or download" button. Copy the URL, e.g., `https://github.com/gladstone-institutes/git-primer.git`, to your clipboard. Then open your terminal to create and enter the repository from the command line:

```bash
git clone https://github.com/gladstone-institutes/git-primer.git
cd git-primer
```

## Work with Git

Check status
```bash
git status
```

Create a new branch named `my-feature`. (Good idea to keep your active development in a separate branch from master so that master is always in the last known good state and production ready.)
```bash
git checkout -b my-feature
```

Make some changes
```bash
mkdir my-dir
touch my-dir/my-file.txt
```

Commit your work (do this often)
```bash
git add ./my-dir/my-file.txt
git commit ./my-dir/my-file.txt -m "create my file"
```

Push to GitHub (remote)
```bash
git push origin my-feature
```

Merge your work into master branch (local). Only do this when work is production ready.
```bash
git checkout master
git merge my-feature
```

Push to GitHub (remote)
```bash
git pull origin master
git push origin master
```

Delete feature branch
```bash
git branch -d my-feature
git branch -d origin my-feature
```
The last command (to delete branch on github) will not work. Look up stackoverflow. 
