# git-primer ([cheatsheet](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf), [docs](https://git-scm.com/docs))
Git a technology that allows you to efficiently save and manage multiple versions of the code for a project. The collection of different versions is called a repository, and multiple users can each have their own repository for the same project. Each repository can serve as a source from which other repositories can pull and a destination to which other repositories can push -- it's distributed. Many sites host git repositories and add a web-based interface, such as GitHub and Bitbucket and GitLab. This primer is focused on using git from the command line, but some people use a GUI, such as [GitHub Desktop](https://desktop.github.com/) or [EGit](http://www.eclipse.org/egit/).

## Get Started (First Time)

```bash
git config --global user.name "Jay Doe"
git config --global user.email jdoe@example.org
```

## Create a Repo (GitHub)
Visit the [Gladstone Institutes group](https://github.com/gladstone-institutes) and click the green "New" button. Fill out the forms, and you'll get a page with instructions on how to create a new repository on the command line, push an existing repository from the command line or import code from a non-git repository.

## Clone a Repo (GitHub)
Visit the desired repository, e.g., [git-primer](https://github.com/gladstone-institutes/git-primer), and click the green "Clone or download" button. Copy the URL, e.g., `https://github.com/gladstone-institutes/git-primer.git`, to your clipboard. Then open your terminal to create and enter the repository from the command line:

```bash
git clone https://github.com/gladstone-institutes/git-primer.git
cd git-primer
```

## Work with Git

Check status.
```bash
git status
```

Create a new branch named `my-feature` and push it to GitHub. It's a good idea to keep your active development in a separate branch from master so that master is always in the last known good state.
```bash
git checkout -b my-feature
git push origin my-feature
```

Make some changes.
```bash
mkdir my-dir
touch my-dir/my-file.txt
```

Commit your work (do this often).
```bash
git add ./my-dir/my-file.txt
git commit ./my-dir/my-file.txt -m "create my file"
```

Sync with GitHub (remote).
```bash
git pull origin my-feature
```

If someone else was working on the branch, you may need to merge their work with yours. Git gives you [many different options](https://git-scm.com/docs/merge-strategies) for doing this, but most often, you can just use this procedure:

```bash
git mergetool
```

Select your preferred tool and complete the merge. If you select Opendiff, just use the GUI and save your merge. If you select Vim, follow these instructions:

>```
> ----------------------------------------
> |            |            |            |
> |   LOCAL    |    BASE    |   REMOTE   |
> |            |            |            |
> ----------------------------------------
> |                                      |
> |                 MERGED               |
> |                                      |
> ----------------------------------------
>```
>
> Use `]c` to jump to the next difference. Then get version from one of the three options above:
> * `:diffget LO`
> * `:diffget BA`
> * `:diffget RE`
> 
> When complete, save and exit with `:wqa`.

Commit your merge (if you needed to merge) and push to GitHub:

```bash
git push origin my-feature
```

When your changes are production ready, merge your work into your local master branch.
```bash
git checkout master
git diff my-feature # optional
git merge my-feature
```

Push to GitHub (remote).
```bash
git pull origin master
git push origin master
```

Delete feature branch both locally and at GitHub.
```bash
git branch -d my-feature
git push origin -d my-feature
```
