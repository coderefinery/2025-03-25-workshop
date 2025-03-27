+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 3"
+++

## Icebreakers

Let's test the notes with some icebreakers! :icecream:

If you could ask for any superpower (can be computer-related), what would you ask for?
- Unlimited, precise refactoring capabilities
- short-range teleportation
- creation of unlimited food to distribute it to people who need it
- teleporting so I can go on more vacations
- Quantum brain

In preparation for today, unless you are part of a team/classroom, have you opended an access request issue in [access request repo](https://github.com/cr-workshop-exercises/access-requests/issues)
- Yes: oooooooooooooooooo
- No:
- What?:
- What?? access request report??

How do you collaborate with others on code? (there are no wrong answers, we are really interested)
- github
- send my dofile to them via email
- github/email/slack
- github/gitlab mostly
- just email before
- scripts on a server +1
- usually don't work on the same code with others +1+1+1+1+1
- I try to use issues/MR, but the others like to do more lengthy in-person discussions (which I cannot attend). Then I "protest" on Mattermost :-)
- I used to use Gitlab
- pdf files and email :(
- talk and shared folders
- GDrive
- gitlab
- Google Collab
- Onedrive


General questions:

- Q. I missed yesterday. Would I be able to follow today
    - In general yes.  The concepts are useful, but you can probably follow even without.


## Concepts
https://coderefinery.github.io/git-collaborative/concepts/

- In Figure explaining Fork and Clone, can you explain "origin"?
  - Origin is the default name for the remote repository, the repository we cloned from. A shorter way to say "github.com/ORGANIZATION/REPONAME.git"

- When you fork, the upstream repository can change, and you can change your own fork. How to reconcile these different developments?
  - Merging (which we will see).  You'll need to do the right merges to combine it together.
  - Also part is being structured enough that merges don't become too complex.  We see some ways to do that today.

- What is the diference between pulling and pushing?
  - Fetch: get code from somewhere else, to your computer
  - Pull: Fetch (above) + merge to whatever the default is
  - Push: put code from your computer somewhere else.  Doesn't merge (you have to pull, merge, then push)
  - It'll become more clear later

- If I have cloned a repo and after a while some changes are made in the upstream. If I again clone the repo to get those changes, will my local changes be still there in my local repo?
  - This is a very good question: updating code is important.  Recommendation: first commit.  Then a "git pull" would merge your changes and  anything new.  But... this is the basic simple way.  For larger projects we'll see a more branching method
  - It also depends on if you have made a fork first.  We'll talk about this some - I suggest asking again at the end of the day.

- Why isn't a template just a matter of cloning a 'template-like' repository that behaves like other repositories?
  - it's a GitHub implementation choice. On GitLab, for example, it works differently.
  - Just cloning, editing to your liking, and pushing to a new repository of your own (likely deleting the original remote repo) would work, and that's likely pretty close to what GitHub does under the hood. But it's easier to have a one-click solution, especially as people aren't often too familiar with fiddling with different remotes


## Same-repository collaboration
https://coderefinery.github.io/git-collaborative/same-repository/

- Does the deletion of a repository deletes a user's activity history?
  - Anything Github has, basically yes
  - It doesn't automatically delete what is on your (or someone else's) computer.

- basic ques. Is commit like saving my changes to my local repo? It doesn't effect the upstream just by committing, ryt?
  - Correct, it affects only the local repository. To affect the upstream/remote repository, you need to additionally push.

- Why my own repository does not have a `Use this template` button on github like [this](https://github.com/coderefinery/recipe-book-template)?
  - It can be configured! in "Settings", at the very top, you can choose if the repository can be used as a template. If you tick that box, then the "use this template" green button will appear on your repo too.
      - I see. Thanks.

- How do I know if I am part of a team?
  - We didn't assign teams this time, it would be if you know someone.  So probably not.
  - if you want to know which repositories you were added to as a collaborator, it is a little tricky. The most reliable way to get this information is to go to `https://github.com/dashboard` (once your are logged in) and look at the list of repositories on the left, clicking "show more" under the list of "top repositories" (If anybody has a better idea, please let me know!)

- Good point that you needed to accept the invitation! I had missed that since I received 3 emails, of which one said "Thanks! I have added you to the collaborative exercise team.", but still I needed to accept the invitation today
  - ^^ Tanks for remarking this, perhaps other people had your same problem.

- Are there some general repository templates on GitHub?
    - There are templates that some research groups share for how to set up e.g. a Python project or a R project. (I will find examples ...)
    - For some kind of projects, [cookiecutter](https://cookiecutter.readthedocs.io/en/stable/index.html) might have templates you could find interesting, but the focus there might not be research code

- It seem that I don't have access right. $ git clone git@github.com:cr-workshop-exercises/centralized-workflow-exercise.git practice_collaboration
  Cloning into 'practice_collaboration'...
  git@github.com: Permission denied (publickey).
  fatal: Could not read from remote repository.Please make sure you have   the correct access rights and the repository exists.
  - I think most likely the SSH key to Github hasn't been set up (setup in install instructions - if it worked yesterday it is probably not this): https://coderefinery.github.io/installation/ssh/#ssh
  - I set up keys yesterday.
  - Hm ok, then probably not that.  This is a public repo so it shouldn't be access-related.
  - Have you gotten an invite and accepted it? Yes, I did. I am part of a group of 45 people.
      - but indeed it should work even if you don't have write access.
  - workaround that I suggest is to do this on the web directly which is anyway interesting to see how that works and that it's possible (I use it for very small things where it's easier than getting the code first to my laptop)
  - you can also test that your ssh keys are correctly set up with: `$ ssh -T git@github.com`. this should produce no error but something like: "Hi USER! You've successfully ..."
     - does this work?
     - ssh test directly to github works for me but pushing to the repo still gives a password prompt and then fails.
         - in this case check what "origin" refers to: `git remote --verbose`. Does it refer to the exercise repo? Possibly you try to push changes to somewhere else.
    - I think I have it - this is because I cloned using https:// URL rather than SSH (git@github.com). If other people are having the same issue after cloning using https:// (which forces the password prompt) change the origin to git@github (git remote set-url origin [ssh url]) and see if that works.

- I am working on VSC and when I wanted to publish the new branch, I got the message of no permission to push that.+1
     - if you are sure that you have write permissions (gotten invite and accepted and you have been added as collaborator), then check that you are pushing to the right place. in a terminal (or the terminal within VSC) you an type: `git remote --verbose` which will show you where origin points to. It should be the exercise repo.

yes. it is the exercise repo. I also tried the gihub web and even ther i don't have the permission to creat a branch. I have already accepted the invitation.
- I've managed to mess up the instructions slightly and seem to have added and fully merged my branch. I missed the instructions where it said to leave it as a draft. Sorry!
     - no problem at all
     - don't hesitate to open new pull request

- I forgot to reference the issue in my commit message. Is it possible to modify the message before I push? +1
  - yes , you can refer the issues on your pull request. We will show that.
  - also on bottom right of a pull request form there is "Development" where you can connect it to an issue.

- I am trying to work on the command window, I made a commit with the commit message "fixes #17", but the you can seeissue is still there. Should the issue have dissapeared?
   - The issue will disappear when your pull request is accepeted and the changes are merged.
ah, so I should push now?
   - yes open a pull request.
that means write git push in the command line right? :)
   - pull request are on the github, after you pushes your changes, on github you create pull request
so first i do git push on the command line and then make a pull request on github in the webbrowser?
   - yes.
Thank you!

- I am trying to push my branch to the remote repository. I have the ssh connection setup for command line, but "git push" request password authentification.
  - It might be that you've cloned the repository with HTTPS (wanting passwods) instead of SSH.  Or SSH keys aren't set up (but then you couldn't clone either)
      - Yes, I used the HTTPS cloning, I thought it will not affect. Do I need to clone again?
  - Cloning again is the easiest solution.  You can also adjust the remote in-place: `git remote set-url origin git@github.com/cr-workshop-exercises/centralized-workflow-exercise.git` (I haven't tested this exactly yet)

- Someone closed my pull request without merging it to the main branch. Is there anything that I can do about it?
   - It can be re-opened. But in real life it is always nice to add a reason for why it was closed. In the next exercise we will practice how to ask for changes in a PR (pull request) without having to close and open a new one.

- I don't really understand the difference between a draft pull request and a pull request?
    - draft pull request cannot be merged. it can be a nice mechanism to collect feedback or inform others that something is in progress. and once it's ready you can "un-draft" it and make it merge-able.

- I seem to have everything required by the check_recipe.py script, but it still shows a red cross on the pull requets page. Issue #4
    -  if you like you can mention the PR number and we can look. but it's not a big problem if the tests fail here, this was only to show that this is possible to do. more about it next week where we go in-depth into automated testing.

- What's the most sensible way to reconcile divergent branches if I didn't clone the repo with tracking? git gives the following options:
   git config pull.rebase false  # merge (the default strategy)
   git config pull.rebase true   # rebase
   git config pull.ff only       # fast-forward only
    - Longer explanation: All of these are sensible options, so this is somewhat a matter of taste and/or agreed practices for the repository. Rebasing is something we haven't in this course, but in short it means that instead of creating a merge commit in which two branches join, it will move the commits from one branch on top of another branch, making it look like they were done one after another. For example [this page from Atlassian](https://www.atlassian.com/git/tutorials/merging-vs-rebasing) illustrates the difference.
    - Shorter answer: if you want things to work the "default" way (the way we have used in this course), you choose `pull.rebase false`, but in some situations the other ones can be useful too

- I accidentally chose "Create pull request" instead of "Create draft pull request". In case of "Create draft pull request", who (which role) will review the draft pull request? Also, after th review, can the same (draft) pull request be merged or does the same contributor need to make another pull request (not draft this time)?
  - A draft pull request is exactly the same as a standard one, except that it cannot be merged until it is marked as non-draft. You can also mark a non-draft pull request as a draft.
  - There is typically no need to make another pull request to update an existing one. Even if you push new commits to the branch you want to be merged, they will be added to the pull request.

- i am working in vscode. i made the new branch and so on in there. when i wanted to merge the branches i wasnt able to do so on vsc. but in github i could do it. whats the reason i could not do it in vscode? if you need the error message please tell me.
  - yes, please: what message did you get?
    -* branch            main       -> FETCH_HEAD
       hint: You have divergent branches and need to specify how to reconcile        them.
       hint: You can do so by running one of the following commands sometime before
       hint: your next pull:
       hint:
       hint:   git config pull.rebase false  # merge
       hint:   git config pull.rebase true   # rebase
       hint:   git config pull.ff only       # fast-forward only
       hint:
       hint: You can replace "git config" with "git config --global" to set a default
       hint: preference for all repositories. You can also pass --rebase, --no-rebase,
       hint: or --ff-only on the command line to override the configured default per
       hint: invocation.
       fatal: Need to specify how to reconcile divergent branches. (does this maybe help?)
    - So, the problem here is that you have commits on your local branch that are not on the remote branch and vice versa. By pulling, git by default does not know what to do: should I merge or do something fancier (rebase)? I would suggest to open a terminal (the one in vscode will suffice, perhaps prefer "git bash" to "powershell" if you are on windows) and type the `git config pull.rebase false` command. Then you should be able to pull and merge without issues. There might be a way to manage the configuration of git from vscode - maybe some other helper can help with this.

- I found it awkward that there was the security measure that we couldn't modify the main remote branch directly, but had to first create a branch (in my case locally), make modifications or additions, then push the branch to the remote, then make a pull request to merge the remote branch with the remote main repository. I know this is a security measure, but wouldn't normally we collaborators just be able to modify local version of main branch and make pull requests with remote main directly?
  - For your other smaller projects, you probably wouldn't turn this on.  (It's not on for most of our projects).  It's on for purposes of this exercise to prevent certain types of problems (and force the demonstration we want)

- If you accidentally closed a pull request, before merging, can this person also re-open it? So not the person who created the request, but the person who closed it.
  - To my memory, yes.
  - I just found it: You have to go to pull requests but closed ones, find it. Then comment and reopen it.
  - Ammendment: This does not reopen the pull request but only the commenting! I think, this has to come from the person initially requesting it.

- In Pull request, do we need to use specific words such as "close" or "fix" before e.g., #24 so that GitHub automatically close the issue? How does this automatic closing issue happen?
  - You don't have to, but the words provide automatic close.
  - It is a Github (+Gitlab) feature that's programed as part of those platforms.  Not a default Git thing.

- (Continued for above) So if we just write #24, that issue won't be closed?
    - Correct, it will be linked but without the automatic close part.

- Is the pull request in github comparable to the merge request in gitlab?
    - Yes! They are pretty much 1:1 counterparts, only the vocabulary and small details in how the additional magic (automatic checks etc) works differ

- aquafaba for eggs...(chickpea water)
    - ah thanks! you can even try to add a commit to my open pull request (if you are on the same exercise repo)
    - and unrelated to git, I really want to try it out
    - truthfully, it is quite fickle. for a pumpkin pie i might rather go with coconut cream, cold water, vegan butter etc depending on what the purpose of the egg is. better for light recipes. but as a general subsitute for frothy egg whites - it does work. not on the *recorded repo so can't add a commit!

- So the new commits are added in the Pull requests which are not yet merged, ryt? If my pull request is accepted then for any new commit, I need to create new pull request?
  - Correct.  You *can* reuse the same branch but also make a new one.

- What is 'codespace'?
    - (I am not using it so my answer might be wrong but ...) I understand it as Visual Studio code in the cloud (browser) which can run in a well-defined environment (dependencies) and has close integration with the repository
    - also one thing you can try is, on any github repo, type the keyboard key "." which opens something VS Code-like

- should we open the issue here again or just make a new branch, make changes and commit?
     - creating a new issue not super necessary since we practiced this earlier. we will come back to it during discussion what the value of this can be. it can be good for larger changes or changes that take more time. many smaller changes don't need an issue to refer to.

- How can one change in which folder where a file (=recipe) is located? Eg I accidentally put a soup recipe in mains and would like to move it to soups
  - on the command line, `git mv`  can be used to move a file to another directory.
    - I think you can just use regular `mv` too?
    - yes you can, but then you need to tell git about that, which means
      ```
      git add <the-old-path-of-the-file>
      git add <the-new-path-of-the-file>
      ```
      so it is 3 commands (mv, git add old path, git add new path) which is much more error-prone and tedious than just using `git mv`, although completely equivalent.
  - On VSCode, one can drag and drop the file from a directory to another, and then in the source control panel one can verify that the file was "deleted" in the old position and "created" in the new one.

- I am not sure how can I directly edit a file in a merge request.
    - click on "Files changed" (top right), then click on the "+" next to the line you want to comment on or change (it can even be a range), then there is a "+-" button where one can suggest changes.
        - did it work?
            - yes, geat. Thanks

- I tried to add a new commit to the same branch locally and then push, but cannot see the change in GitHub, what did I do wrong?
  - You might need to update the web page with F5? Otherwise, make sure the push was successful (without error messages).
- What is the difference between starting a review and adding a comment ?
  - To my understanding, "review" means that, after you comment and suggest changes, you approve or reject the pull request. But in GitHub/GitLab it is a little more vague than that, because "review" means that you can also just leave a comment or a code suggestion. The difference is more evident when you are explicitly requested as a reviewer - then you might need approve/reject the PR for the review to be complete.

- So although I only changed one file on my remote branch which didn't trigger the test, due to another change on another file which I pulled from the latest version of the repo the test is now failing on my next commit :( however I can't push without having the latest version of the repo. Have I made mistakes while updating my remote branch?
    - I am having the same issue. i think it is because the creator of a breakfast sandwich has not organised the recipe correctly according to python.
    - How did this sandwich recipe pass the automated tests before merging then? Or does the test not actually block a pull request from completing if you don't ask for review? Curious!
    - in this case we did not configure github to prevent us from merging a failed test. it can be done. possibly a failed test got merged (not a problem here) and then affected subsequent changes. we wanted to demonstrate this because it is something that happens in reality. but during code review we then also look at test status (in case we have tests).
    - Failing tests do not prevent PRs from being merged, by default, because it can happen - and often, in many projects, unfortunately it does - that some "small" tests fail and make the whole test suite fail, but might not be "that important" to the level of blocking everything. This is a slippery slope, BUT sometimes being able to integrate new changes even if the checks as a whole fail could be the lesser evil. Just try not to end up in this situation.
        - there are also situations where we find out that the test itself had a flaw and then merging a "failing" change can be good and later we adjust our assumptions about the tests.
        - In that case, the PR should also contain a fix for the test, if that is possible. But we're all humans with limited resources, so the best we can hope for, realistically, is that "soon enough" the workflows/pipelines get fixed
- What doesn failing check means after committing?
  - We have a script which Github uses to verify things are what they should be (we learn in detail on day 6)
  - This is Github verifying this.
  - ... or is this somewhere else?
     - yes this is the script (here happens to be Python but can be any language): https://github.com/cr-workshop-exercises/centralized-workflow-exercise-recorded/blob/main/check_recipes.py
     - this is the workflow: https://github.com/cr-workshop-exercises/centralized-workflow-exercise-recorded/blob/main/.github/workflows/check-recipes.yml
       - in short: we tell github to run the script on any merged pull request to main
     - but we will use this more and explain this better next week

- Where can I find day 2 exercises? it seems each day removes previous notes? kiitos. i am a bit confused as we have a lot of links flying around =)
  - here you can find the notes from day 2: https://coderefinery.github.io/2025-03-25-workshop/questions/day2/
  - and in general, the pad from each day is archived and made available here https://coderefinery.github.io/2025-03-25-workshop/questions/
  - We do have a lot of links, true! The material for the last 2 days was https://coderefinery.github.io/git-intro/

- Are there AI agent who reply out quesiton now?
  - Yes, I am one.
  - Great =)
      - but don't worry, no robots are training here on your questions yet. once we publish it on the internet, then unfortunately the robots will crawl our pages at some point.

- My pull request is still waiting for merging in the collaborative repository. I made a git pull and now the file I modified disappeared from my local clone. How should I do a git pull to avoid this kind of situation?
  - Actually, a `git pull` command cannot "remove files" from your local clone, BUT what it likely happened is that upstream, in the remote repository, someone made changes that moved/removed that file and when you do `git pull` you merged in those changes. If you want to avoid that, and get back to the status of your directory before you made the pull, you can use git log to find the last commit that you liked (e.g., the one before the merge), and then do `git switch -c new-branch <last commit you liked>`. Yet another alternative is to use `git fetch` instead of `git pull`, and that will only get the changes without performing a merge. You will be able then to peek into the changes before, with, for example `git switch -c remote-main origin/main`.

After the break we will summarize previous exercise and then go to ...


## Contributing changes to repositories that belong to others
https://coderefinery.github.io/git-collaborative/forking-workflow/

- people using cmd line - please use ssh (git@gitlab) not https:// to clone the new repo to prevent problems with your SSH key!
    - Can you explain what the problem would be here with using https?
        - You cannot push back to the remote if you use https.

- CATS

- When would you use this forking workflow, vs what we did before lunch, vs direct pushing?
    - Fork: when you don't have permission to push directly to the repo
    - Direct push: when you have the permission to do so (your own repo, or e.g. a repo shared between a research group)

- I'm a bit lost. Are we supposed to be forking the centralized-workflow-exercise repo?
     - no, fork the  https://github.com/cr-workshop-exercises/forking-workflow-exercise-recorded or  https://github.com/cr-workshop-exercises/forking-workflow-exercise
          - they look the same but write permissions are different (imagine these "belong" to only Dhanya and me)
          - I see. Thank you!

- "3. Make a change to the recipe book on the new branch and in the commit cross-reference the issue you opened. See the walk-through below for how to do this." Can't see excatly where the walkthrough for this is. I can only see that for pull request upstream NOT cross reference commiting
    - Good point. It seems we moved this to earlier exercise and did not update text. But what this meant is like previously that I can refer to an issue number in the commit message or pull request title or text to close it once merged, e.g.: "adding lemon to recipe soandso, closes #14" (which will then auto-close number 14)
    - All of this will be happening on my new branch and forked repository?
        - the issue is typically on the original repository. the commit happens on your repository. and the pull request is between the two. once the pull request is merged and the default branch on the original repository is updated, it will auto-close the issue. we forgot to discuss why that is useful but will do that in the discussion session.

- 4. I deleted my-branch from the remote repository on Github. When I then used "git pull" on the command line, the remote/origin/my-branch is still in the list of branches. The local branch is also still there. How should we delete branches in github work and can it also locally remove the branch?
  - Does `git pull --prune` remove the `remote/origin/my-branch` ?
      - yes this removed the branch remote/origin/my-branch
  - Your own branch (`my-branch`) isn't affected by deleting on Github.  It needs to be deleted separately.  We haven't talked about this yet
  - `git branch -d my-branch` will delete safely (it won't delete it if it's not merged, make sure you pull/fetch first), `git branch -D my-branch` will delete no matter what.

- [I'm using VSCode] Should I push/publish to my forked repo or to the upstream repo?
  - in the forking workflow, that's the procedure - you push to your fork, not to the original.
  - But if you want to contribute to the main project, once you have everything done, you want to push/publish to the upstream repo, which creates a pull request - don't it?
  - A pull request is not created by a push, it needs to be explicitly created. You push to your fork, then you can create a pull request (the web interfact on github will typically suggest this once you have pushed)
      - Thank you
      - Happy to be useful!

- I understand how to do "Update your fork with changes from upstream". How about cloned repo in my local computer? How do I update my repo in the local computer from upstream?
  - Once you have updated your fork on github, you do "git pull" on your computer. Alternatively, if you have also registered the original repo as a repository, you can also pull directly from there.
  - ` git remote add upstream [repo url]` worked for this, then you can do `git pull upstream [branch]` or whatever reference you use for the remote (doesn't have to be "upstream"). this bypasses the web interface entirely to update your personal fork from the original repo.

- (continued from above) Thanks, but how do I do that in VS code? Click Synchronize change once fork repo in GitHub is updated from upstream?
    -  yes I think so (I would need to try to reconfirm since it's been a while I tried that on VSC)

- pull requests from others are only seen in my fork after they have been merged, right?
    - Yes, should be.  (merged to upstream + your fork synced to upstream)
    - To be precise: the commits that others have done and is included in their pull requests will appear in your fork once the pull requests are merged and you sync your fork.

- Can you go over 'fetch' and 'pull'? +1
  - I think this might be discussed live on stream. But, in a nutshell:
    - fetch: grab the changes in a remote repository, store them in some 'hidden' local branches (that you can see with `git branch -a`)
    - pull: same as `fetch` but in addition try to do a merge (or other things) to your properly "local" branches that are "connected" to the remote ones.
    If you do 'pull' instead of 'fetch' and you regret, there are a couple of "rewind buttons" that you can use - if you're interested I can tell more

- What is the difference between "deleting branch" and "deleting origin/branch"? (VS code)
  - Deleting branch should delete the branch on your local repository. If you refer to the command "Delete Remote Branch", it tries to delete the branch on the remote repository (this should be equivalent to `git push --delete <branch-name> <repository>`).

- Just for understanding: Why not sync the created branch instead of main with the upstream repo?
    - it's technically possible but we imagine that code changes flow from branches to central main, from central main to forked main, and then to newly created branches. in this case you probably want to keep your feature branch (the branch that holds the new change) "undiluted" until it is integrated. this can make review easier because the review will only show the "undiluted" change (if that makes sense but please ask more if this answer is not clear)
        - very clear thanks

- Creating pull requests from codium needs some extra installations, do you have a recommendation? Or is it better just using github for this.
    - Oh, good to know. (I don't have an anwser, I always make from github.com or command line)  Anyone have an answer?
    - (Is it possible directly from VSCode without extra extensions?)
    - It is possible to do PRs from VSCode: https://github.blog/news-insights/product-news/create-pull-requests-in-vscode/#:~:text=To%20create%20pull%20requests%20in,ve%20opened%20your%20pull%20request. But it does require the GitHub Pull Requests extension. Personally, I think it's no issue adding an extention if it simplifies your work.

- Why don't you just fork a repository, clone it to your local machine, and make changes there, then push changes to remote fork, then make pull request for mergeing remote fork with origin? Why always make a branch locally when no one is modifying the local main?
  - It in theory works to work on `main` directly.  If you are sure it won't be modified, it technically works
  - But: what if you forget and do other stuff on main?  What if it's not immediately merged and `main` stays occupied with that change for a while?  What if `main` has other stuff on it already?  You can consider these trade-offs when deciding what to do.
    - But just having local main accumulate other changes would not be a problem ultimately, yes? Those changes would be merged with remote main in the end, yes?
        -Oh....(actually I didn't understand what you said about the weird history)
        - But it seems counter to the philosophy of a 'branch' and what a pull request should be (i.e. commit to branch rather than branch to branch...). I thought a 'branch' was like 'your working version of a repository'.
        - A commit is actually 'your working version of a repository'. A branch is a series of commits, it represents the 'history of your repository in time'. The fact is, at any given time, a branch points to a single commit (but this commit changes over time). I think this is where the confusion comes from - a branch can be confused with a commit because of this.
        - Oh. Ok.

- I am not sure if I would use issues a lot as I could do also some discussions and comments in a merge request. Can you please comment on it?
  - It's a typical problem I have with my collaborators - which kind of discussions should go in an issue, and which should go in a PR? But there's one thing for which issues are needed: before a PR exists, just to discuss whether or not a problem exists (e.g., report it, have a reproduction case...). Then, once a PR is opened, it becomes a little hard to tell where the discussion should go.
      - makes sense, thanks
      - In other words: if I am using open source software, and I encounter a problem that I do not know how to solve, typically I create a new issue (previously checking if there is any issue that mentions the same problem to avoid duplicates)
  - yes I often observe that the discussion starts and evolves until the pull/merge request is open and then sometimes continues in the merge request. not a problem since they are ideally cross-referencing but it can get confusing when discussion continues in parallel in both places and it fragments the discussion. one can also write nicely on the PR: "let's discuss here the changes but for the big picture we continue on the issue?" or "let's continue discussion on the PR?" - even more problematic I find when discussion happens also in parallel on some chat which might be hard to read for future generations who only see the PR or issue later.

- Were you going to talk about how to do version control with Overleaf docs in GitHub? I thought you mentioned that.
  - You can read some here: https://www.overleaf.com/learn/how-to/Git_integration
  - In short, you can `git clone` with a special path and authentication to get the overleaf project as a local Git repository, and also push back.
  -

- Can we access the HedgeDoc content after this workshop?
  - It gets saved on the workshop website: https://coderefinery.github.io/2025-03-25-workshop/questions/


## News for day 3 / preparation for week 2

- Today, we went over the topics as listed in the schedule and did all exercises.
- Next week: still using Git/Github, but now applying to different tasks
- Next week is all demos, no exercises (there are exercises, but too involved to fit into the day - you can do them later)
- You can definitely attend next week if you didn't this week - if you know git, you can follow it all.  If not, you'll see ideas you can study more and apply later.


## Feedback

Today was (vote for all that apply):
- too fast:
- too slow:
- right speed: oooooooooooooooooooo
- too slow sometimes, too fast other times: o
- too advanced:
- too basic:o
- right level: oooooooooooooooo
- I will use what I learned today: oooooooooooooooo
- I would recommend today to others: ooooooooooooooo
- I would not recommend today to others:

One good thing about today:
- I realised how much I learned the past two days, because a lot got faster today.+1+ 1+1+1+1+1+1
- I liked that more was explained, before the exercises started+1+1+1
- giving an optional additional exercise for the forking exercise was appreciated! +1+1
- Talking about branching, forks, the whole process of handling collaboration with pull requests.
- Learned to know to create a branch always, instead of push to the main branch +1+1
- This session is a good complement to yesterday's: we're going deeper into the concepts, and it feels like what we saw yesterday is informative.
- Have the feeling my muscle memory is fed:) +1+1
- Really nice format of first telling what is familiar and what will be learned

One thing to improve for next time:
- I think stepwise instructions for this exercise purely on command line (as with the other days) might be informative, for people who prefer not to necessarily have to revert to the web interface? +1
   - thanks! we had them in older versions but removed them because they became distracting for those following on web but we can find a good balance and let people choose. I am aware that for command line it now assumes that people remember commands from earlier which is not realistic.

Any other feedback?
- Today was fun+1+1+1+1
- I would actually like a small document covering purely the exercises and solutions for review and future replication, rather than the complete set of lessons. Possible to produce at the very end of the course?
  - There is actually a page with a list of all the exercises in a lesson in the "reference" section of the navigation bar. Solutions are not there but the original episode is linked.
  - This page: https://coderefinery.github.io/git-collaborative/exercises/ (it's raw insertions may miss some context)
- Thanks a lot for your effort and work!!!+1+1


## General questions continued

- Do you have favorite webpages to look up git commands (if you forget, how they work)?
  - Very useful if you have problems: https://dangitgit.com/en
  - I made this that focuses on different levels of complexity and shows everything I think most people need: https://aaltoscicomp.github.io/cheatsheets/git-the-way-you-need-it-cheatsheet.pdf
  - If you know the terms for different areas, this is convenient: https://ndpsoftware.com/git-cheatsheet.html - but we haven't gone over some of the columns.
  - Maybe the lesson's reference: https://coderefinery.github.io/git-collaborative/reference/
- How similar are the functions we learnt today in GitLab?
  - Very similar.  "Pull Requests" becomes "Merge Requests" (but it's only a name change) and different web layout, but essentially everything directly translates.
  - GitLab has more stress on Merge Requests, which are like pull requests but in the same repository (no need to pull in that case). But GitLab uses also the term 'merge request' for the same concept involving two repositories, which implies a pull.

- I registered for only this week. Can I attend next week as well. It appears I can't register again as my email is also associated with this week's registration. Will I get the materials and link that is sent out every morning and after the sessions?
  - I think you should be able to amend your registration?  If not email us.
  - But even if you don't manage to edit your registration, please join us next week as well.  Livestream is obviously open to all and notes is the same.
  - Yes please join!

- I did but it says: "There is already a registration with this email address." and it does not allow the register button to be enabled when I click on it.
    - You do not need to re-register, but to edit the existing registration: In the email with the title "[Indico] New registration for Online CodeRefinery workshop March 25-27 and April 1-3, 2025", click on here in "You can manage your registration here". Found it?
    - Yes, thanks.
