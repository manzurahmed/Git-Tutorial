# Git Tutorial from Hasin Hayder

Hasin Haydar bhai has a very nice video tutorial series on Git in his YouTube channel in Bengali. He covers various aspects of Git in a very friedly and helpful manner.
Here is the link: https://www.youtube.com/watch?v=M2a7OQX8te4&list=PLoR56CteKZnC0lBlHdnVnq0J3yDhgbi9w.

### How to install Git on Windows 10 PC

Download Git from https://git-scm.com/downloads and install on your PC using default options. Run "Git BASH" to start managing your Git repositories.

## Clone a github repo on local pc using git

In order to clone a GitHub repo, copy its URL. In your PC, start Terminal or Command Promp and navigate to your folder where you would like to clone the repo. Type the following command:

```
git clone https://github.com/manzurahmed/reactjs-techsith
```

Git will create a new folder called **reactjs-techsith** and download all files in that folder.

# Video 01: Intro

গিট (Git) হল কোডের একটি জনপ্রিয় ভার্সন কন্ট্রোল সিস্টেম।
যখন কয়েকজন ডেভেলপার মিলে একটা প্রজেক্টে কাজ করেন, তখন প্রজেক্টের কোড খুব সহজে ম্যানেজ করার জন্য গিট ব্যবহৃত হয়। গিট খুবই ফাস্ট। এটি অনলাইন ও অফলাইনে কাজ করা যায়।

আজ আমি একটি ফাইলে কাজ করার পর যদি ডিজাইরেবল আউটপুট না পাই এবং আগের দিনের স্টেটে ফেরত যেতে চাই, তবে, ঐ ফাইলে অতি সহজেই ফিরে যাওয়া যাবে। আবার, ডিলিট করা ফাইলও ফেরত আনা যায়। 

গিট এ কাজ করতে হলে মূলত: ৩ টি কনসেপ্ট সম্পর্কে পরিষ্কার আইডিয়া থাকতে হবে।

1. git commit - লোকালি যে কাজ করেছি তা রেকর্ড করা
2. git push - লোকালি করা কাজ সার্ভারে তুলতে হলে
3. git pull - সার্ভারে থাকা কোড লোকাল পিসিতে আনতে হলে

এছাড়াও, যা জানতে হবে:

1. git status
2. git add
3. git diff
4. git log
5. git show
6. git reset
7. git branch
8. git checkout
9. git merge
10. git stash

# Video 02: Init, commit, log

### git init
কোন প্রজেক্ট ফোল্ডারে গিট ব্যবহার করতে হলে প্রথমেই এই কমান্ড দিতে হয়। ঐ ফোল্ডারে একটি **.git** নামে একটি hidden ফোল্ডার তৈরী হবে। পুরো প্রজেক্টে **মাত্র একবার** এই কমান্ড ব্যবহার করতে হয়।

**নোট**

কমিট করার আগে গিটের লোকাল প্রোজেক্টে ব্যবহারকারীর আইডেনটিটি সেট করতে হয়। এর জন্য কমান্ড ফাইনে নীচের কমান্ড দু'টি ব্যবহার করতে হবে।

```
git config --global user.email "youremailaddress@example.com"
git config --global user.name "github_id"
```

### git config --global credential.helper cache

যতবার গিটহাব থেকে pull বা push করব, Terminal এ ততবার লগইন ক্রেডেনশিয়াল (username এবং password) টাইপ করতে হয়। গিটহ্যাব বর্তমানে পাসওয়ার্ড সাপোর্ট করে না। তার পরিবর্তে Token ব্যবহার করতে হয়। এই কারণে গিটের গ্লোবাল সেটিং এ username এবং token সেট করে নিতে হয়।

Terminal এ উপরের কমান্ড দেয়ার পর git pull বা git push করলে যখন username এবং password চাইবে, সেটা দেয়ার পর পরবর্তীতে আর username এবং password চাইবে না।

### git status

গিটে সব ধরণের এ্যাকটিভিটি সম্পর্কে রিপোর্ট পাওয়ার জন্য এই কমান্ড ব্যবহার করা হয়।
ধরি, আমাদের ফোল্ডারের মধ্যে একটি নতুন ফাইল "index.html" তৈরী করলাম। এই অবস্থায় যদি এই কমান্ড ব্যবহার করি, তবে দেখাবে যে একটি untracked file প্রোজেক্ট ফোল্ডারের মধ্যে রয়েছে। এই ফাইলকে git add দিয়ে প্রোজেক্টে যুক্ত করতে হবে।

### git add
নতুন ফাইল গিটে যোগ করতে হলে এই কমান্ড ব্যবহৃত হয়। index.html ফাইলকে গিটে যোগ করতে নিচের কমান্ড ব্যবহার করব।

```
git add index.html
```

**নোটঃ** git add index.html দিয়ে নতুন ফাইল যোগ করার পরে যদি নতুন ফাইল বাদ দিতে হয়, তবে git reset index.html কমান্ডটি দিতে হবে।

### git commit -m "added index.html file"
লোকালি কোন মডিফাইড কোন ফাইলকে গিটে সেভ করে রাখার জন্য git commit কমান্ড ব্যবহৃত হয়; আর সাথে -m প্যারামিটার ব্যবহার করে একটা নোট দিতে হয়। কি কারণে, বা কি ধরনের ফাইল এ্যাড করা হচ্ছে, তা এখানে লিখতে হবে। এখানে -m অর্থ Message।

### git commit -m "Give a meaningful message here." <file-name-1.txt> <file-name-2.txt>
কোন **নির্দিষ্ট মডিফাইড ফাইলকে** গিটে সেভ করে রাখার জন্য

### git commit -am "Some files are change"
একাধিক ফাইলে একসাথে কমিট করতে চাইলে,
কিন্তু, এভাবে কমিটি করলে কোন ফাইলে কি চেঞ্জ হয়েছে তা উল্লেখ করা যায় না।

### git diff
গিটে কোন কোন ফাইলে কি কি মডিফাই হয়েছে, তা দেখার জন্য

### git log

গিটের কোন রিপোজিটরিতে প্রথম থেকে কি কি commit করা হয়েছে, তার রিপোর্ট পেতে।

**নির্দিষ্ট একটি ফাইলের লগ** দেখতে চাইলে,

```
git log filename.txt
```

সংক্ষিপ্তাকারে লগ দেখতে চাইলে, এই কমান্ড দিব:
```
git log --oneline
```

### git show 0602b93c79bd28e5f306124f7d9cddc42a0f8a15

প্রত্যেক ফাইলের কমিটের একটা করে hash number থাকে। যেমন: "commit 0602b93c79bd28e5f306124f7d9cddc42a0f8a15"
কোন কমিটের হ্যাশ নাম্বার দিয়ে কি চেঞ্জ করা হয়েছে, তা দেখতে চাইলে এই কমান্ড ব্যবহার করতে হবে।


# Video 03: Back, Reset, Ammend

### git checkout 0602b93c79bd28e5f306124f7d9cddc42a0f8a15

প্রজেক্টের পূর্বে অবস্থায় ফিরে যেতে চাইলে প্রথমে git show দিয়ে যে কমিটে ফিরে যেতে যান, তার হ্যাশ কোড কপি করে নিন। এরপর git checkout কমান্ড দিন।

**ভয়াবহ জরুরী সতর্কবার্তা**

- **কমিটের ঐ হ্যাশ কোড এর মুহূর্ত এর পরে যে সমস্ত ফাইলগুলো প্রজেক্টে যোগ করা হয়েছিল এবং যত ধরনের এডিট করা হয়েছিল, তার সবই ভ্যানিস হয়ে যাবে**।
- আগের অবস্থায় ফেরত আসতে চাইলে, নিচের কমান্ড দিন,
```
    git checkout master
```

### git checkout 0602b93c79bd28e5f306124f7d9cddc42a0f8a15" new.txt

- পুরনো কমিটের শুধুমাত্র **নির্দিষ্ট একটি ফাইলকে পূর্বের কমিটে ফেরত নিয়ে যেতে চাইলে**, হ্যাশ নাম্বারের পরে ঐ ফাইলের নাম দিয়ে দিতে হবে, যেমন:

```
git checkout 0602b93c79bd28e5f306124f7d9cddc42a0f8a15" new.txt
```

- এই অবস্থায় যদি মনে হয়, যে আমার কমিটে ফিরে যাওয়া ভুল হয়েছিল, তবে নিচের কমান্ড দিন,

```
git checkout master -f
```

তার মানে হল, শুধু একটা ফাইলকে কখনও চেকআউট করার পর আগের অবস্থায় ফেরত যেতে হলে, -f প্যারামিটার যোগ করতে হবে।

### Reset

- কোন ভুল কমিট থেকে ফেরত আসতে গেলে reset করতে হবে। তবে, এই কমান্ড ব্যবহারে সতর্কতা নিতে হবে।
- **কোন কমিট push করে দেওয়ার পর ভুলেও reset ব্যবহার করা যাবে না**।

reset দুই রকম।

- হার্ড রিসেট
- সফট রিসেট

সফট রিসেট হচ্ছে, আগের চেঞ্জগুলো রেখে ব্যাক এ যাওয়া।
হার্ড রিসেট হচ্ছে, আগের চেঞ্জগুলো মুছে ব্যাক এ যাওয়া।

**Reset Soft**

ভুল কমিটের পর Soft reset এ ঐ ফাইলের পুরনো কমিট পর্যন্ত যাবে, তবে ঐ কমিটের পরে ফাইলে যে কাজগুলো করা হয়েছে, তা থেকে যাবে।
```
git reset --soft 0602b93c79bd28e5f306124f7d9cddc42a0f8a15" 
```

Soft reset অবস্থায় diff দেখতে হলে, নিচের কমান্ড দিন,
```
git diff HEAD
```

**Reset Hard**

```
git reset --hard 0602b93c79bd28e5f306124f7d9cddc42a0f8a15" 
```

### গিট এর হিস্টরি দেখার জন্য,

![Git Reflog screen shot](Git-Tutorial/images/git-reflog.jpg)


```
git reflog
```

"**git reset --hard**" কমান্ড দিয়ে পূর্বের কোন কমিট এ ফিরে যাবার পর মনে হয়, আগের কমিট এ ঠিক ছিল, তবে git reflog কমান্ড থেকে যে কমিট এ ফিরতে চান, তার HEAD@{} এর হিস্টরির নাম্বার টা নিয়ে নিচের ২ টা কমান্ড দিতে হবে,

```
git reset HEAD@{8}   [Note: কার্লি ব্র্যাকেটের মধ্যে হিস্টরির নাম্বারটা হবে আপনি যে কমিট এ ফিরতে চান, তার নাম্বার]
git reset --hard
```

**রিসেট বিষয়ক ওয়ার্নিং**

- কোন কমিট যদি পুশ/পাবলিশ করা হয়ে যায়, তাহলে ভুলেও রিসেট করবেন না।
- শুধুমাত্র যেসব কমিট পুশ করা হয়নি, সেগুলোর ক্ষেত্রে প্রয়োজন হলে রিসেট ব্যবহার করুন।
- পুশ/পাবলিশ করা কমিটের ক্ষেত্রে রিভার্ট ব্যবহার করুন।

### git commit --amend

আগের কমিট এর সাথে যদি নতুন ফাইল যুক্ত করতে হয়, তবে প্রথমে যে ফাইলটি যুক্ত করতে হবে, তা git add দিয়ে যুক্ত করে নিয়ে git ammend কমান্ড দিতে হবে।

```
git add test2.txt
git commit --amend
```

### এ ছাড়াও জানতে হবে

- branch
- merge
- stash

# Adding an existing project to GitHub using the command line
1. Create a new repository on GitHub. To avoid errors, do not initialize the new repository with README, license, or ```gitignore``` files. You can add these files after your project has been pushed to GitHub.

2. Open Terminal.

3. Change the current working directory to your local project.

4. Initialize the local directory as a Git repository.

```
$ git init -b main
```

5. Add the files in your new local repository. This stages them for the first commit.
```
$ git add .
# Adds the files in the local repository and stages them for commit. To unstage a file, use 'git reset HEAD YOUR-FILE'.
```

6. Commit the files that you've staged in your local repository.
```
$ git commit -m "First commit"
# Commits the tracked changes and prepares them to be pushed to a remote repository. To remove this commit and modify the file, use 'git reset --soft HEAD~1' and commit and add the file again.
```

7. At the top of your GitHub repository's Quick Setup page, click to copy the remote repository URL. 

8. In Terminal, add the URL for the remote repository where your local repository will be pushed.

```
$ git remote add origin  <REMOTE_URL> 
# Sets the new remote
$ git remote -v
# Verifies the new remote URL
```

9. Push the changes in your local repository to GitHub.
```
$ git push origin main
# Pushes the changes in your local repository up to the remote repository you specified as the origin
```

# How can I create a Git repository with the default branch name other than "master"?

Since git version 2.28.0 the git init command now takes a --initial-branch (or -b for short) parameter. These two commands create a new Git repo with a branch named "trunk", which always made more sense to me than "master" (master of what?):

```
git init --initial-branch=trunk
git init -b trunk
```

This is configurable with the init.defaultBranch setting. If I want all new repos to have "trunk" as the default branch:

```
git config --global init.defaultBranch trunk
```


# Renaming the Local master Branch to main

The first step is to rename the "master" branch in your local Git repositories:

```
$ git branch -m master main
```

Let's quickly check if this has worked as expected:

```
$ git status
On branch main
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

So far, so good! The local branch has been renamed - but we now need to make some changes on the remote repository as well!

Source: https://www.git-tower.com/learn/git/faq/git-rename-master-to-main

# Create a new branch

## Check the list of branches in a project
```
$ git branch
```

## Check the list of branches in Remote GitHub

```
$git branch -r
```

## Check the list of branches in local repository

```
$git branch -a
```

## Create a new Branch
```
$ git branch feature1
```

I can create a new branch and navigate to the branch with git checkout:
```
$ git checkout -b feature1
```

## Navigate to a branch
```
$ git checkout feature1
```

## Git Merge

To merge a branch in master (main) branch, first, go to the main branch.

```
$ git checkout main
```

Then issue the merge command:

```
$ git merge feature1
```

## Delete a branch

```
git branch -d feature1
```


# How to add a local repository to GitHub

Follow this official guideline on GitHub:

https://docs.github.com/en/get-started/importing-your-projects-to-github/importing-source-code-to-github/adding-locally-hosted-code-to-github

# git set-upstream

The git set-upstream allows you to set the default remote branch for your current local branch. By default, every pull command sets the master as your default remote branch.

Sometimes we are trying to push some changes to the remote server, but it will show the error like "error: failed to push some refs to 'https :< remote repository Address>." There may be the reason that you have not set your remote branch. We can set the remote branch for the local branch. We will implement the following process to set the remote server:

To check the remote server, use the below command:
```
git remote -v  
```

It will result as follows:

```
git remote -v
origin  https://github.com/manzurahmed/puppeteer.git (fetch)
origin  https://github.com/manzurahmed/puppeteer.git (push)
```
Now, check the available branches, run the below command:
```
git branch -a
```

The above command will list the branches on the local and remote repository. To learn more about branches, click here. Now push the changes to remote server and set the particular branch as default remote branch for the local repository. To push the changes and set the remote branch as default, run the below command:

```
git push --set-upstream origin main
```

The above command will set the master branch as the default remote branch.

Source: https://www.javatpoint.com/git-upstream-and-downstream
