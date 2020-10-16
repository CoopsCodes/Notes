## To configure git user details

```js
	git config --global user.name "<name>"
	git config --global user.email "<email>"
>
```

---

## creating repositories

👇 initialise a new repository

```js
	git init

	// => Initialised empty Git repository in <filepath>
```

👇 to check if a repo exists

```
	ls -a
```

if a repo exists there will be a `.git` file

👇 staging files

once changes are made and you want to commit those but selecting all, one or multiple files

```js
	git add .
	// => the . command will select all files to commit

	git add index.html
	// => will select the named file to commit

	git add file.js fileone.css filetwo.html
	// => will target multiple files to commit
```

👇 UNstaging files

say we want to reverse a file we just staged

```
	git rm --cached <file>
```

👇 committing added files

```js
	git commit -m "<description message>"
```

👇 check the details of the gid directory

```
	git log
```

---

## reverting back to a previous commit

Say we make a boo boo and want to revert back to a previously committed state.

This is possible with checkout, first grab the hash from the previous commit through `git log`, the hash is the alphanumeric combination after commit i.e. `bdd9a77e85512eb0836d532716e1dbf2889ceeb8`

```
	commit bdd9a77e85512eb0836d532716e1dbf2889ceeb8
	Author: Cooper Viktor <im.cooperviktor@gmail.com>
	Date:   Wed Aug 19 17:21:48 2020 +1000

    JavaScript Classes example
```

👇 and we checkout to that with hash

```
	git checkout bdd9a77e85512eb0836d532716e1dbf2889ceeb8
```

👇 this will move you out to a new branch and can be identified with, this will show you the current branch

```
	git branch
```

👇 to move back to the main branch

```
	git branch main
```

---

## making new and changing branches

to create a current snapshot of the code and branch off and work in a new codebase without working in main, we create a new branch

```
	git branch <name>
```

this will create a new branch, but you'll still be on main

👇 so make sure you move to it with

```
	git checkout <name>
```

so what happens now you've done a good load of work on a branch and you want to merge it into your main repository?

first you want to change into the branch you want to merge it into, this could be the main branch or maybe you're merging a hotfix into a sub branch, point is you go to the branch you want to merge your work into (`git branch <name>`)

👇 then we use merge the feature branch

```
	git merge <name>
```
