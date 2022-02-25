---
# try also 'default' to start simple
theme: default
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  Introduction to using git and GitHub
# persist drawings in exports and build
drawings:
  persist: false
layout: intro
---

# Using <img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" class="h-20" alt="git"/>

A short introduction

<style>
  img {
    display: inline;
  }
</style>


---

# What is git?

- git is a decentralized version control system
- GitHub is an online platform for hosting and collaborating on git repositories

---

# Why do we care?

- Version control is great!
- If you go into industry, you'll be expected to use a version control system
- If you stay in academia, publishing code on GitHub (or similar, e.g. GitLab, BitBucket) is a convenient way to share your code and make your work reproducible

---

# Version control: naive approach

<v-clicks>

- <carbon-document /> thesis_v1.tex
- <carbon-document /> thesis_v2.tex
- <carbon-document /> thesis_v2_bmw_edits.tex
- <carbon-document /> thesis_final.tex
- <carbon-document /> thesis_final_final.tex

</v-clicks>

<v-clicks>

This is a bit painful, but it works...  We don't have any history of what changes happened in each version, though, which would be nice <noto-v1-thinking-face />

### Now we need to collaborate... 

### over email... <carbon-email /> 

### <noto-v1-face-screaming-in-fear class="text-6xl" />

</v-clicks>

---

# Version control: using a version control system (vcs)



### <carbon-document /> thesis.tex

- change 1
  - Author: so and so
  - Summary: created latex template
  <!-- - List of changes: ... -->
- change 2
  - Author: so and so
  - Summary: frantically wrote entire thesis
  <!-- - List of changes: ... -->
- change 3
  - Author: bmw
  - Summary: fixed figure placement
  <!-- - List of changes: ... -->
- change 4
  - Author: so and so
  - Summary: reverted bmw's changes...
  - List of changes: ...


---

# Example of version history in git

---
layout: section
---

# git basics

---

# Cloning repositories

```bash
git clone [url]
```

<br/>
<br/>
<br/>
<br/>

## Exercise
Clone the git-practice repository:
```bash
git clone git@github.com:BMW-lab-MSU/git-practice.git
```
OR
```bash
git clone https://github.com/BMW-lab-MSU/git-practice.git
```

---
layout: two-cols
---

# Making commits

- commits record snapshots of your files permanently in version history
- we need to add files to the snapshot before we can commit anything

<br/>
<br/>

### Example:

- add fizzbuzz function
```bash
git add fizzbuzz.py
git commit -m 'added fizzbuzz function'
```
- make some changes to fizzbuzz...
```bash
git add fizzbuzz.py
git commit -m 'fixed bug in fizzbuzz'
```

::right::

<img src="/commit-graph.svg" class="h-4/5 absolute bottom-5" />

---

# Pushing changes

<br />
Now that I've committed some changes, I need to push them to the "remote" (e.g. GitHub)

```bash
git push
```

<br />

<img src="/local-vs-remote-push.svg" />

---

# Pulling changes

<br />
We could have the opposite situation: the remote has changes that I don't have locally

```bash
git pull
```

<br />

<img src="/local-vs-remote-pull.svg" />

---

# Exercise

- pull the changes from the remote into your local git-practice repo
- create a markdown file `firstname-hello.md` with the following
```markdown
# Hello World

**bold**
*italic*
- bullet
- points
```
- add/commit/push the file to the remote

---
layout: section
---

# Branches

---

# What are branches?

- Basically a pointer to a commit/snapshot
- Independent from any other branch
- Allow you to work on a feature or bug-fix without affecting the main branch or other people

<br />
<br />

<img src="/branches.svg" class="h-2/3" />

---

# Making branches

- make a branch
```bash
git branch [branch name]
```
- checkout a branch
```bash
git switch [branch name]
```
OR (older way)
```bash
git checkout [branch name]
```
- push the branch to the remote
```bash
git push --set-upstream origin [branch name]
```

---

# Excercise

- make a branch called `fizzbuzz-firstname`
- at the end of fizzbuzz.py, print your name:
```python
print('so and so')
```
- push the branch to the remote

---

# Merging branches / pull requests

<br/>

Once we are done with our branch, we want to merge the changes back into another branch (usually "main" or "dev")
- Can be done with git commands or with pull requests

<br/>

#### merge from git
```bash
git switch -c main
git merge [branch name]
git push
```
<br />

## Pull requests
 - a place to compare and discuss the differences introduced on a branch with reviews, comments, integrated tests, and more

---

# Pull request example

---

# Exercise

- create a pull request for your fizzbuzz branch
- we will merge all the branches!

---
layout: section
---

# Archiving code with releases

---

# Publishing code with our papers

- make your results reproducible!
- help future researchers!

<br />
<br />
<br />

## We can do this with [Zenodo](https://zenodo.org/)
- https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content

1. Add GitHub repository to your Zenodo account
2. Create a release on GitHub!
3. Mint a DOI and feel good <noto-v1-beaming-face-with-smiling-eyes /> <noto-v1-smiling-face-with-sunglasses />
4. Cite the DOI in your paper!


---

# Resources <dashicons-welcome-learn-more />


## git cheat sheet

https://training.github.com/downloads/github-git-cheat-sheet/

## Atlassian git tutorials
https://www.atlassian.com/git/tutorials

## git documentation
https://git-scm.com/doc


