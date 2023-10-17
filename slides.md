---
# try also 'default' to start simple
theme: eloc
# https://sli.dev/custom/highlighters.html
highlighter: prism
# show line numbers in code blocks
lineNumbers: false

title: 'Intro to Git'

# some information about the slides, markdown enabled
info: |
  ## Git intro
# persist drawings in exports and build
drawings:
  persist: false

# enable pdf download in SPA build
download: true
exportFilename: 'intro-to-git'

selectable: true

aspectRatio: '16/9'

# disable presenter mode in build, but allow in dev
presenter: dev

transition: fade

# force light mode
colorSchema: 'light'


class: 'text-center'
---
<div class="flex flex-row  justify-between w-9/10">

<div>
<img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" class="h-300px" al6="git"/>
<br>
<!-- insert presentation information here -->
</div>

<div>
<qrcode-vue :size=300 /> 
<br>
follow along!
</div>
</div>

<presentation-url class="text-center absolute bottom-20" />

---

<img src="/phd-comics-not-final.gif" class="h-full">

---
layout: statement
class: 'text-center'
---

# Why use version control?

<div class="flex flex-row justify-between w-full h-full items-center">
  <div v-click class="grid grid-rows-2 gap-y-2 text-center justify-items-center">
    <flat-color-icons-collaboration class="text-70"/>
    <i>collaboration</i>
  </div>
  <div v-click class="grid grid-rows-2 gap-y-2 text-center justify-items-center">
    <mdi-test-tube class="text-70 text-blue-500"/>
    <i>reproducibility</i>
  </div>
  <div v-click class="grid grid-rows-2 gap-y-2 text-center justify-items-center">
    <mdi-cloud-upload class="text-70 text-green-500"/>
    <i>backups</i>
  </div>
</div>

---
layout: statement
class: 'text-center'
---

# Version control in academia

<div class="flex flex-row justify-between w-full h-full items-center">
  <div v-click class="grid grid-rows-2 gap-y-2 text-center justify-items-center">
   <mdi-file-code-outline class="text-70 text-purple-500"/>
   <i>software</i>
  </div>
  <div v-click class="grid grid-rows-2 gap-y-2 text-center justify-items-center">
   <mdi-robot-industrial class="text-70 text-amber-500"/>
   <i>designs</i>
  </div>
  <div v-click class="grid grid-rows-2 gap-y-2 text-center justify-items-center">
   <mdi-fountain-pen class="text-70 text-blue-500"/>
   <i>writing</i>
  </div>
  <div v-click class="grid grid-rows-2 gap-y-2 text-center justify-items-center">
   <mdi-code-brackets class="text-70 text-green-500"/>
   <Link to="zenodo"><i>citations</i></Link>
  </div>
</div>

---
layout: section
---

# Types of version control

---

<div class="grid grid-cols-2 gap-40">

<div class="flex justify-center">

## Centralized


<img src="/vcs-comparison-centralized.svg">

</div>

<div class="flex justify-center">

## Decentralized


<img src="/vcs-comparison-decentralized.svg">

</div>
</div>

<style>
  h2 {
    @apply absolute top-5 text-center;
  }
</style>

---

<div class="flex flex-row justify-between w-9/10 h-full text-center content-center place-items-center">

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" class="h-200px" al6="git"/>

<img src="https://imgs.xkcd.com/comics/git.png" class="h-full">

</div>


---
clicks: 3
---

# git building blocks
<ul>
  <li v-click="1"> <b>commits</b>: a snapshot of your files* </li>
  <li v-click="2"> <b>commit graph</b>: commits are organized into a <i>directed acyclic graph</i> </li>
</ul>

<br>

<div v-click="3" class="relative -left-110 top-10">

### history

</div>

<arrow v-click="3" x1="350" y1="640" x2="350" y2="520" color="#f59e0b" width="6"/>

<div v-click="1">

*if git is *tracking* the files

</div>


<style>
  p {
     font-size: 0.5em;
  }
  h3 {
    @apply text-amber-500;
  }
</style>


---

<img src="/commit-graph.svg">

---
layout: statement
class: 'text-center'
---

# Create a repository

<a href="https://github.com/new">https://github.com/new</a>

---
layout: statement
class: 'text-center'
---

# Clone the repository <mdi-download-box class="color-blue-500" />

`git clone`


---
clicks: 9
---

# The basics

<v-clicks>

- `git add`
- `git commit`
- `git push`
- `git pull`
- `git status`
- `git log`

</v-clicks>

<div v-click="7" class="absolute left-1000px top-350px text-amber-500">

#### committing changes

</div>

<div v-click="8" class="absolute left-1000px top-520px text-blue-500">

#### interact with GitHub

</div>

<div v-click="9" class="absolute left-1000px top-680px text-red-500">

#### view what you've done

</div>

<div v-click="7" class="absolute left-900px top-295px">
<svg width="100" height="500" class="stroke-amber-500">
<polyline points="0,40 80,40 80,190 0,190" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="8"/>
</svg>
</div>

<div v-click="8" class="absolute left-900px top-455px">
<svg width="100" height="500" class="stroke-blue-500">
<polyline points="0,40 80,40 80,190 0,190" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="8"/>
</svg>
</div>

<div v-click="9" class="absolute left-900px top-615px">
<svg width="100" height="500" class="stroke-red-500">
<polyline points="0,40 80,40 80,190 0,190" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="8"/>
</svg>
</div>


---
layout: section
---

# The three trees

---

# File states

<div class="flex flex-row justify-between w-9/10 items-center">

<p class="text-blue-500 text-7xl">modified</p>

<mdi-arrow-left-right class="text-9xl color-gray-500"/>

<p class="text-green-500 text-7xl">staged</p>

<mdi-arrow-right class="text-9xl color-gray-500"/>

<p class="text-purple-500 text-7xl">committed</p>
</div>

---

<img  class="absolute top-0 h-screen" src="/git-three-trees-overview.svg">

<img v-click="1" class="absolute top-0 h-screen" src="/git-three-trees-annotated-add.svg">
<img v-click="2" class="absolute top-0 h-screen" src="/git-three-trees-annotated-commit.svg">
<img v-click="3" class="absolute top-0 h-screen" src="/git-three-trees-annotated-full.svg">




---

# The index / staging area

- staging changes: `git add <files>`
- viewing the index: `git status`

---

# Committing changes

`git commit`

- only changes in the staging area are added to the commit
- commits need a *commit message*

---

# Viewing changes

- working tree <mdi-arrow-left-right /> staging area: `git diff`
- staging area <mdi-arrow-left-right />  HEAD (the parent commit): `git diff --staged`

---

# Exercise

1. modify the contents of your `README.md` file
2. stage those changes (`git add`)
3. commit the changes (`git commit`)



---

# Viewing history

`git log`

---

# Exercise

1. create a new file: `test.md`
2. write stuff in `test.md`
3. add `test.md` to the staging area
4. commit your changes

---
layout: section
---

# Commit philosophy

<emojione-thinking-face class="text-50"/>

---

# When to commit?

<v-clicks>

- you complete a *logical, atomic unit* of work
- you might want to undo those changes

</v-clicks>

---

# What to commit?

<div class="flex flex-row justify-between w-6/10">
<div v-click class="text-center">

### do commit
<hr>

- source code
- design files
- documentation

</div>
<div v-click class="text-center">

### don't commit
<hr>

- build artifacts
- large data files

</div>
</div>

---

# Commit messages

<div class="flex flex-row justify-between w-9/10">

<div v-click class="text-center">

### philosophy
<hr>

- tell a *story* of your project's history
- capture *why*

</div>
<div v-click class="text-center">

### content
<hr>

- short summary
- extended description

</div>
</div>

---
layout: statement
class: 'text-center'
---

<div class="text-8xl">
oops! <emojione-bug /> <emojione-grinning-face-with-sweat />
</div>


<br>

# Reverting changes


`git revert`

---

# Exercise

1. revert your first commit

---
layout: section
---

# Interacting with GitHub

local vs. remote repositories

---
layout: full
---


<img class="h-screen" src="/local-vs-remote-repos-local-changes.svg">


---
layout: full
---


<img class="h-screen" src="/local-vs-remote-repos-local-changes-push.svg">

---

# Exercise
#### *pushing* to GitHub (the "remote" repository)

1. verify that your local branch is ahead of the remote
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `git status`
2. push your local changes to the GitHub repository (remote)


---
layout: full
---

<img class="h-screen" src="/local-vs-remote-repos-remote-changes.svg">

---
layout: full
---

<img class="h-screen" src="/local-vs-remote-repos-remote-changes-pull.svg">

---

# Exercise
#### *pulling* from GitHub

1. edit a file and make a commit using your repo's GitHub webpage
2. pull those changes into your local repo

---
layout: section
---

# Tags and branches

a commit by any other name...

---

# Tags

<img src="/tags-and-branches-tag.svg">

<v-click>

`git tag -a v0.1`

</v-click>



---

# Exercise

1. tag your most recent commit as `v1.0`

---
clicks: 1
---

<div class="absolute top-1">

# Branches

</div>

<img v-click-hide="1" class="absolute bottom-0" src="/tags-and-branches-branch.svg">
<img v-click="1" class="absolute bottom-0" src="/tags-and-branches-branch-2.svg">

<style>
  .slidev-vclick-target {
    transition: none;
  }
</style>



---

# Branching commands

- create branch: `git branch <branch-name>`
- change current branch: `git switch <branch-name>`
<!-- - changing branches: `git checkout <branch-name>` -->
<!-- - both at the same time: `git switch -c <branch-name>` -->

---

# Exercise

1. create a branch called `cool-feature` and switch to it
2. add `hello from cool-feature branch` to your `README.md`

---

## Merging branches

<img src="/tags-and-branches-merge.svg">


---

# Merging branches

`git merge <branch-to-merge>`

- need to be in the branch you want to *merge into*


---

# Exercise

1. switch to your `main` branch
2. merge `cool-feature` into `main`

---

## Typical feature branch workflow

```mermaid {scale: 1.4, theme: 'base'}
gitGraph:
  commit
  commit
  commit
  branch feature1
  checkout feature1
  commit
  commit
  checkout main
  merge feature1
  commit tag: "v1.0.0"
  branch feature2
  commit
  commit
  checkout feature2
  commit
  commit
  commit
  checkout main
  commit "v.1.1.0"
  branch feature3
  checkout feature3
  commit
  commit
  checkout main
  merge feature3 tag: "v1.2.0"
  checkout feature2
  commit
  checkout main
  merge feature2
  commit tag: "v2.0.0"
```

---

<div class="flex flex-row w-full justify-between items-center">

<mdi-presentation class="text-200 text-blue-500"/>

<mdi-arrow-right class="text-150 text-amber-500" />

<qrcode-vue :size=500 />

</div>

<presentation-url class="absolute bottom-20" /> 


---
layout: section
---

# Bonus slides

<emojione-party-popper class="text-50" />


---
routeAlias: zenodo
---

## Archiving code with <a href="https://zenodo.org/">Zenodo</a>

<div class="text-6xl text-center">
assign DOIs <mdi-code-brackets class="text-green-500"/> to your code <mdi-file-code-outline class="text-amber-500"/>
</div>

- [random example](https://zenodo.org/record/8370339)
- [how to](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content)

---

# Resources <emojione-books />

<div class="flex flex-row justify-between w-8/10">
<div>

- [git - the simple guide](https://rogerdudler.github.io/git-guide/)
- [GitHub Git Guides](https://github.com/git-guides/)
- [Atlassian git tutorials](https://www.atlassian.com/git/tutorials)
- [Think like (a) Git](https://think-like-a-git.net/)
- [Git best practices](https://sethrobertson.github.io/GitBestPractices/)

</div>
<div>

- [Command line Git](https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html)
- [Pro Git book](https://www.git-scm.com/book/en/v2)
- [GitLab git cheat sheet](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)
- [GitHub git cheat sheet](https://training.github.com/downloads/github-git-cheat-sheet/)
- [The art of the commit](https://alistapart.com/article/the-art-of-the-commit/)

</div>
</div>


---

Playground: <a href="https://git-school.github.io/visualizing-git">https://git-school.github.io/visualizing-git</a>

<iframe src="https://git-school.github.io/visualizing-git" title="https://git-school.github.io/visualizing-git"></iframe>

