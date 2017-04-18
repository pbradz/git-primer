# git-primer

## Creating a GitHub Repo

Visit the [Gladstone Institutes group](https://github.com/gladstone-institutes) and click the green "New" button. Fill out the forms, and you'll get a page with the following instructions.

### Creating a new repository on the command line

```
echo "# git-primer" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:gladstone-institutes/git-primer.git
git push -u origin master
```

### Pushing an existing repository from the command line

```
git remote add origin git@github.com:gladstone-institutes/git-primer.git
git push -u origin master
```

### Importing code from a non-git repository
You can initialize this repository with code from a Subversion, Mercurial, or TFS project. See GitHub for more details.

## Working with Git

Check status
```
git status
```

Create a new branch named `my-feature`
```
git checkout -b my-feature
```

Make some changes
```
mkdir my-dir
touch my-dir/my-file.txt
```

Commit your work (do this often)
```
git add ./my-dir/my-file.txt
git commit ./my-dir/my-file.txt -m "create my file"
```

Merge your work into master branch (only do this when work is production ready)
```
git checkout master
git merge dev
```
