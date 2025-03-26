+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 2"
+++


## Icebreakers

Let's test the notes with some icebreakers! :icecream:

- What was the last animal you saw?
  - shield bug
  - was human, just changed to CATS
  - cats +1+1
  - my dog +1
  - crow
  - my dog
  - people with dogs
  - my cat
  - Big dog +1
  - Alligator
  - Jackdaw
  - pipsa possu
  - human o
  - seagull
  - jumping spider
  - a blind orange cat, not mine
  - Dog
  - silverfish bug
  - 3 Goldfishes

- Which path did you you use yesterday to interact with Git?
  - GitHub: ooooooooooooooooooooooooooo
  - VSCode: oo
  - Command line: ooo
  - I was not here yesterday (no problem): o
  - I wished you offered a path for a different tool:
    - JupyterLab (git integrated as plugin, also available on CSC Puhti interactive JupyterLab, very convenient and beginner-friendly)
    - ..


## Any questions from yesterday?

1. How do you set up the webpages for the tutorials/documentation at https://coderefinery.github.io/?
   - We'll talk about this on day 5!  It's basically here: https://coderefinery.github.io/documentation/gh_workflow/

2. Is there anything you want us to repeat today?

3. I did not really understand why I need tags
    - If you want to say "version 1.0", that should be a fixed thing.  Branches change, tags shouldn't.  (When you update you would make "version 1.1")
    - In research: E.g. if you use a specific version for your paper you could tag it with "nature_submission" indicating that this was the version used for submission to nature. That tag stays there, at exactly that version whether you later change stuff or not and you can go back to exactly that version of the code easily. If you would create  a branch "nature_submission", this branch could be altered later on, new commits added to it etc. but a tag would just stay with the commit you tagged. Essentially, a Tag is a more human readable variant of a commit hash that allows you to indicate one specific version.

4. Where is the instructions for the first exercise of today?
    - Here: https://coderefinery.github.io/git-intro/local-workflow/#exercise

5. Is there any difference between using 'git clone' versus downloading the ZIP archive?
    - `git clone` links it to the Github repo, which means you can get updates and merge with your changes easily.
    - Download zip gets you only the files - any updates are on you.
    - I usually do `git clone` since it's as easy and I can get future updates if needed (and see any modifications I made)


## Local work (cloning)
https://coderefinery.github.io/git-intro/local-workflow/

6. Step (3) Creating branches locally = for this one do we need to be in the same directory of recipe-book?
   - yes!  The "current working directory" is very important and you should always be aware of it.

7.  🚨 In step (3), I think the arrow in the screenshot of the solution for VS code is pointing at the wrong dots, it should be the three dots next to "Changes", not the three dots next to "source control".
    - Oh thanks.  I wonder if something changed between then and now.  What do other people see?
    - You're correct. It should be the three dots from "Source Comtrol -> Changes". Alternatively, one may click on th ebranch name at the bottom of the window and then create a new branch.
    - I have used the Github issue tracker to make a note about this.  Thanks!

8.  What is the difference between `git switch` and `git checkout`?
    - `git checkout` was the original one and did several very different things (changed files, changed branches)
    - `git switch` was added a few years ago and *only* changes branches.  Most computers updated in the last 5 years should have `git switch` now.

9. How do you know which branch you are on when working on the command line?
    - `git status` - always a good thing to run, often! +1
    - alternatively, `git branch` it will add an asterix next to the branch name

10. Is it possible to make git use, e.g. `vim` instead of `GNU Nano` for merge messages and stuff? I always have to look up how to quit, because I am not used to `GNU Nano`.
    - Yes!  If you search `git editor vim` (or whatever) you will probably see how to do it very easily.
    - Thanks! Found it! For anyone: `git config --global core.editor "vim"` (or any other of your choosing)

11. Only for the merge or for everything?
    - For the editor question above?
    - Yes.
    - Everything would be fine too. `git log` I can easily quit, because it is similar to `vim` but the editor always gets me :D
    - The git editor config is used for any editor started from Git.  You can use other editors for files you are directly editing.
      - Thanks for the clarification.

12. In step (4), I dont see +  sign to add the file for the next commit (in VS Code).
    - Me neither
    - VSCode I guess.  Does anyone know where it is now?
        - Make sure you have opened and modified the file. Then go to Source control -> Changes and you'll see the list of modified files. Next to the file name, the "+"
            - it worked.
    - Do you need to be in the "source control" tab on the left sidebar? (Ah but my codium is still old so maybe not up to date..)

13. Do we have to cd into the cloned directory before creating the branch?
    - Yep!

14. I did everything like in the walk through but when i want to merge the two branches the new files i added in the new branch dont show up in my main branch. i dont understand why?
    - Hm, hard to say.  Maybe we can look at the demo and show commands to figure out the situation
    - `git log --oneline --all --graph --decorate` tells us some of what's going on (but, we only learn about this in the next hour)
    - it worked. i think the problem was that i named my branch also new-recipe like yesterday. i changed the name and other worked.
    - Thanks, good to know!

15. Can GitHub Desktop also be used to perform these steps?
    - I think Github Desktop integrates Git + an editor so you can do everything there.  (Can someone confirm)
    - In general, there are *many* programs that do all these steps.  Once you know the concepts, search whatever editor/environment you want to use and you can find how to do it.  Highly recommended.

16. What is this page, where presenter is pasting the code from github? Where the presenter is working right now....is it some word document, it cannt be. Ti AM REFERRING TO THE LIVE SESSION ONGOING. No, i mean the presenter who is speaking and presenting and writing the commands. thanks
    - Was it the "clone" code or the other git commands?
    - Most of this is on the lesson page, under the "Command line" path: https://coderefinery.github.io/git-intro/local-workflow/#solution-and-walk-through  (there might be some extra thrown in there, but this is the main part)
    - Or do you mean the view in which there are all the commits listed on top of each other with a branching and merging line going on the left? That's output from `git graph` configured in [this (optional) part of the git setup](https://coderefinery.github.io/git-intro/configuration/#useful-alias-for-the-command-line)

17. The output from git commands is shown with less instead of printed to the terminal, even if the output is really short (e.g. two lines from `git branch`)
    - This can likely be prevented by setting `git config --global core.pager "less -FX"`: `less` is the usual default pager, and the added `-FX` means that it will just print the contents if it's short (instead of entering the "interactive" mode with less than one page of content to view)

18. So we have to use 'git add' even on files in the repo we only modify and do not create, in order to commit those changes to the repo?
    - Yes! This allows you to choose not to commit everything at once (if you e.g. end up making unrelated changes without committing in between)
    - Convenient shortcut is doing `git commit -a` to commit every modified (but not new) file at once.

19. I fell from the train already +1 +1
    - It's OK!  It is fast.  We are doing this for a recording and you can follow up later.

20. Assuming I have VSCode installed. Is there a wiki page/youtube for setting up/linking my github with it. I have performed the exercise via the command line already but it will be good to know VScode as well especially since it serves as a good editor. Thanks. The instructions send from https://coderefinery.github.io/installation/ only sends to me to install github but not the getting started with GitHub, that's why I asked.
    - We cover this in our install instructions some (that's about the extend I know, others can say more), but you can probably find much more online.
    - Based on [these docs](https://code.visualstudio.com/docs/sourcecontrol/github#_authenticating-with-an-existing-repository), I'd say that it should prompt login when you perform your first git actions that require logging in to GitHub

21. When it came time to merge the another-recipe branch with the main branch, I was taken to a vi session with a file saying I had to add some comments. It was annoying b/c I am not comfortable with vi. Will this always happen with merge operations?
    - If you set a different "git editor" it will open what you request.  I think we have a page on this in the install instructions.  It's good to update for what you need.

22. I am already strugling with ssh. When I wrote Z:\>ssh -T git@github.com I got  git@github.com: Permission denied (publickey).
    - It's OK.  You can resume at the next exercise and figure this out later.  We know this is the first place many problems start happening.
    - did you write "Z:\>" before ssh -T git@github.com? Drop it :)

23. How can i figure it out? I have no idea what to do :D
    - This is just a demo, mainly for recording.  We will re-sync soon.
    - I had the same problem, ssh was working yesterday, but today I had to configure it again by adding the key again to the ssh agent https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent and to my github account https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

24. Can we talk about what HEAD means, and how it relates to origin/HEAD, etc? In the branch list, it shows e.g. remotes/origin/HEAD, remotes/hummus-recipe versus remotes/alex/salad-recipe.
    - HEAD tells you "where you are now", or perhaps more accurately it answers the question "if you were to create a commit now, which commit would be its parent?". origin/HEAD is a bit more hairy concept for me, kind of your local git's idea about where the new commits would be likely to appear in the remote repo? I'm hoping someone has a better answer to this.

25. would it be possible to share commands before hand so that one can easily follow you are executing them? It is easy to get lost if you move eyes to another screen just for a second.
    - Some of the commands are in the lesson from yesterday https://coderefinery.github.io/git-intro/commits/ under the command line tab. But as the focus was on GitHub yesterday, I understand it is difficult to follow.

26. A very basic question: does changing the directory locally using 'cd' on the command line also change the branch?
    - No - these are mostly unrelated

27. OK but then I don't understand the connection between a local directory and the local clone
    - The local clone is placed into a directory.  Git tracks internally (within that directory) what is the current branch and adjusts files to that branch, within that directory.

28. I tried configuring git and all that, but when I'm trying to  git switch --create another-recipe main OR master, I have fatal errors in both cases fatal: invalid reference: master. Why this is?
    - Hm.  Is it an existing repository that already has stuff in it?  If there are no commits yet, you might get this.  Your repo might only have `main` and not `master`, so only the first will work.
    - If you are unusre which branches exist in the remote, you can get a list using `git branch --all`. Do you see `main` or `master`?

29. Just to be sure. Does a commit only affect one file? Or can it affect multiple files?
    - It can affect one or more files! You can `git add` multiple files if you want, but you can also just add one even if you have modified multiple files
    - Very often, it should affect more files, if the changes in one file are related to changes in other files. (It is difficult, though, to change more files simultaneously from the github  web interface).


## Inspecting history
https://coderefinery.github.io/git-intro/archaeology/

30. I do not understand what the output from git grep is supposed to be. When I run it, it gives nothing
    - You need to add an argument for `git grep`. In this exercise, `git grep "Logic error in degree_correlation"`
    - I did that. I gave it the .md file I had just created git gtrp "abc"
    - try going with cd to the main recipe directory and searching for salt with: git grep salt
     - Does the file you created  contain "abc"?
     - For the exercise, work with the nextworkx repo, if you wish.
     - Thank you! The file was indeed empty. I had thought it would also search for titles of files.

31. what do stage and unstage do in VSC?
    - Staging and unstaging mean the same thing whether you are using VSCode or plain command line. Staging a file (or some changes in a file) means that they will be included when you create a new commit with `git commit`. Anything not staged (or unstaged after initially staging if you realize that you didn't want to include some change after all) will not be included in the commit.

32. Where did I get the individual commit hash again (for git show HASH) using either the web interface or command line?
    - Using the web interface, vscode or the command line?
      - using the command line, typically you get a commit hash with `git log` (and other incarnations), or `git blame` (a less nicely named version of `git annotate`).
    - For the exercise, you may `git annotate <file>` where `<file>` should be replaced by the name of the file that contains "Logic...", so `git annotate networkx/algorithms/threshold.py`. Look for the line that contains "Logic error...". At the left of it you will see the hash of the commit that last modified that particular line.

33. The latest commit hash looks like '90544b4fa5' for me and not '90544b4fa'
    - Yes.
    - They are equivalent. They are both, actually, truncations of a much larger commit hash (which is 32 character long), and typically all git commands for all intent and purposes accept truncated versions of hashes as long as they represent unambiguously a full hash (typically 6 or 7 characters are enough for this)

34. A comment on bisect: I usually have tests, so I don't need it, BUT it happens from time to time that my tests take very long to run, so I do not run them for all the commits I do. In that case, I might run them only once in a while, and then, if an error is found, I use bisect to find the commit where I introduced the bug.
    - Nice!

35. How do run a specific commit. When i run bisect it tells me that it got to commit 251, how do i tell python that I want to run commit 251 to check whether that is the offending one? and then go back to bisect to see whether the error was introduced before?
    - Git can switch to that commit by using various commands. For example, `git switch --create good-commit 251`, which will "switch" to that commit and also create a branch named 'good-commit' there. You can also use, if you do not want to create a branch, another command - `git checkout 251` - but it is a weird command.
    - When I run `git switch --create bad-commit 251` it gives me `fatal: invalid reference: 251`
    - I got 251 from `git bisect bad master
Bisecting: 250 revisions left to test after this (roughly 8 steps)
[5c6fb09b319ae1f2e09933afce65e825d8c72c77] commit number 251`
       - I am assuming that `251` here is the beginning of a commit hash that you found at some point, for example with `git log -n 1` sorry no! `git log --oneline | tail -n 1` (this gives you the *first* commit in the history, while `git log -n 1` gives you only the most recent commit).
       - Ah no, sorry! The commit "number" is irrelevant here. You need the commit *hash*. And that's the large number that starts with `f0ea9` (the other one `25b6` is the last, bad commit).
       - Thank you
       - Sorry for the confusion!

36. Is it considered bad practice to commit in-progress, untested changes instead of small, tested ones, when thinking about keeping past versions working?
    - For bigger, more mature projects, it's probably not so good (but yo ucan commit to your development branch incomplete stuff and fix up later).  For small projects I do anything, I'm the only user and it's better to track incomplete stuff than not.

37. In step (2) of the exercise, when I run git annotate networkx/algorithms/threshold.py, I get a lot of output in the command line and I don't know how to enter the next command. The "$ git" does not appear, only ":".
    - To exit, press 'q' (this is the typical way to exit a *pager*, which is the little application that takes the git output and displays it in this case, without actually printing it as output in the command line)
    - Thank you!

38. How can I compare the graph locally and on GitHub by VSC?
    - (I am answering but don't know VSC well enough, please correct my answer ...) To my knowledge you need an extension to see the graph locally in VSC. But alternative in VSC is always to open the terminal inside VSC and run "git graph" in there (which uses the alias/shortcut defined during the course).
    - You need an extension, for example https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph
    - There is a "GRAPH" window in the "Source Control" tab. If you refer to that, there is a similarity with what you see in the "Insights/Network" graph, but it has a different scale and the one on GitHub displays less information by default, and is more focused on displaying branches/pull requests between different repositories than the GRAPH widget on VSC, which is focused on displaying individual commits.

39. What do we mean by remote branch? There is also something called origin in the VSC. Does it mean the original repository we cloned?
    - Yes, origin is typically the original repository that was cloned. "The" remote branch is a branch on the remote repository that typically has the same name as "the" branch on the local repository (there are typically multiple branches both in the local and in the remote repository). Branches on different repositories that are "connected" in this way can be updated automatically with push/pull.

40. Is there a way to see on the command window wich branches there are.
    - In the terminal, you can type `git branch` and it will show the branch you are on.
    - In order to see the remote branches as well, do `git branch --all`

41. what are we doing after lunch in todays workshop?
    - From your own files that are not in git yet, make a repository and share it.   The "last step" before you can really use this yourself.
    - Then a "practical advice / how much of what we teach do we actually do?"
    - Thanks

42. Anyone else had issues setting up VS code?
    - Installing VSCode or making Git/GitHub work with it?

43. These 2 links are some helpful videos (from the CodeRefinery youtube page) I used to set up Git and SHH keys on my local machine's command line.
Git Configuration -- https://www.youtube.com/watch?v=WdDTp8NeHBs
Setting up SSH keys -- https://www.youtube.com/watch?v=XCDg1mtaA5I

44. What Extensions are recommended for visualization in VS Code? So far, I have been using  "GitLens" and "Compare Folders".
    - Anyone use VS code know?  By default it can do the basics, so you don't technically need anything.

45. Super Mario Brothers music??
    - This is a theme song someone made a while ago for CodeRefinery


## Turn project to Git repo and share it
https://coderefinery.github.io/git-intro/sharing/

46. Problem in command line version: remote: Support for password authentication was removed on August 13, 2021.
    - In order to connect to github, one alternative approach is to use `ssh`  authentication.
    - You need to use the "SSH" method, not "HTTPS".  Instructons talk about this (HTTPS can work with an authentication helper, but that's extra)
    - In other words, When you clone the repository (in this case the `remote add origin` command), you need to choose 'ssh' instead of 'https'. This requires to have your ssh keys set up, though.

47. Why do I need to manually create a repository on github instead of just pushing my new local repository directly?
    - Because `git push` cannot automatically create a repository on GitHub for you. At least not yet, maybe they'll introduce it as a feature at some point.
    - To be fair, there are some GitLab servers that allow exactly that - push your local repository, and a remote repository will be automatically created. But this is not the case for GitHub, as far as I know.
        - Cool!
    - GitHub does have its own CLI tool that can do this directly, it can be convenient sometimes. (But needs to be installed separately)
        - Thx for adding this.
    - The reasoning behind this not being possible might have something to do with the fact that if I could just e.g. `git remote add origin git@github.com/myuser/nonexistent-repo` and then start pushing, what should the repository's configuration be like: should it e.g. be public or private?
      - And also typos/misspellings could make unexpected things you might not realize for a while
    - GitLab documentation about this, documenting their approach: https://docs.gitlab.com/topics/git/project/ (just to feed this digression - sorry :-) )

48. In command line, I get the following error message when I try to push my repository.
    - fatal: 'origin' does not appear to be a git repository
        - It seems that you have not created and/or defined what the remote repository should be. If you `git remote --verbose`, you should be able to see soemthing like:
      ```bash
      origin	git@github.com:mygithubusername/myproject.git (fetch)
      origin	git@github.com:mygithubusername/myproject.git (push)
      ```
    - My bad, I forgot the command `git remote add origin` which initialy returned me an error. Now it works, thanks.
      - Great.

49. How can I delete a repo locally? I would like to clone it again using ssh and not https.
    - rm using the command line or in a file explorer
    - You might need to use `rm -rf <directory-containing-repository>`, but be careful with this message! But you can also change the remote url using the command `git remote set-url origin <the-ssh-url-instead-of-the-https-one>`.
        - Thank you!

50. After trying VSCode for this exercise, I feel like I may not go back to command line very often as VSCode makes life easier. What do you think of this? +1
    - There are things that in VSCode are hard to do than on the command line. But true, VSCode (and also every other IDE) offers convenient shortcuts for the most basic workflows (my opinion)

51. Why do I need to set `git branch -M main` before I push to the host? `-M` is supposed to rename a branch even if target exists, but I don't understand why it is necessary at this point.
    - Was the name "master"? That's the default in old versions of git.
        - No I initialized with `git init -b main`, so it was `main`
    - I bet it was to make sure everyone's branch is called `main` even if some previous steps were missed, so instructions would work for everyone. (if it's already called `main` then nothing happens).
        - That's what I thought, and that is why I was confused. :D Thanks for clarification.
        - So, in your case, you did not really need to do that, but the folks having `master` as their default branch name would have needed that step.

52. After moving a file to a newly created directory in my repo, it seems I may have lost any change tracking on that file. It shows only last commit after I moved it into the directory
    - Actually, if the file is moved with relatively few changes, git can detect that it was moved and keep the history, by default. It is a little puzzling that you do not see its history. Have you checked with `git log <name of the file>`?
    - This sometimes happen if you both move the file "normally" (e.g. rename in a file browser or `mv` from command line) and edit the file: then git might think that you removed one file and added a new one that just happens to resemble the old one. One way to avoid this is to do the `mv`, commit, and then edit. An even better option is to move/rename the file using `git mv`. That lets git know that despite the new name, it's still the same file, and git can preserve the history even if you edit it heavily while renaming.

53. Hi, earlier i asked the question about the use of editor but did not undertood the response. I think someon has deleted the question now. Could you talk abou the editor, which editor you use/recommend?) I am referring to the editor where presenter was writing her code, in the session before lunch. I am not sure if editor is the right word for that...
    - Are you referring to terminal based editors like vim or GNU or GUI based editors like VS Code?
    - There are many editors one can use: VSCode is common, but also many that work from the command line.  Sometimes, `git` asks you to enter/edit something (like a commit message).  You can configure what editor pops up in those cases (it can be your main one, or a different one)
    - You can set this.  Some of the editors need special config to work properly.
    - It is really user dependent. I recommend an editor that people around you use, so you can easily ask for help. Since me and my group work a lot with python, I use pycharm, which also enables git control. For my thesis in LaTex I use VSCode. However, I prefer `git` in the command line, because that is, how I started. So you see: It really depends on what your preference is.

54. Does the synchronize button in VSCode mean the same as push on the terminal?
    - Yes.

55. Can you explain the use of the label 'origin' in the repository structure?
    - 'origin' is the default name for the remote repository. If you clone a repository from, let's say, github, the repository on github becomes the "remote" called 'origin'. It is just a conventional name, one could use other names for remotes, and if by any chances more than one remote exist, the second one needs to have another name. Does this answer your question?
    - Uh, sort of. I though I saw the label 'origin' in the repository names we worked with in the exercises locally. Maybe that was from the recipe book repositories cloned from GitHub?

56. Also, when you go to GitHub to create the remote repository matching your local one, does the name have to be the same (as the directory on your local machine?
    - no, it can be any. When you set up the local repository so that it connects to the remote one, you give it the remote url so that it can do it - and it does not have any constraint. Obviously, it reduces the cognitive load to use the same name for the same things everywhere.

57. In Exercise, for VSCode path, we clicked "Publish to GitHub" in Source Control. Is it possible to get "Publish to GitLab" button there as well. I assume we need to install extension like GitLab Extension and some further set up?
    - Both VSCode and GitHub are nowadays owned by Microsoft, thus they are so well connected. I don't use VSCode+GitLab myself, but based on quick googling it seems doable to get them working together reasonably nicely, see e.g. answers [in this StackOverflow question](https://stackoverflow.com/questions/53525536/gitlab-and-visual-studio-code).

58. Could you talk a bit about SSH keys, what they are and why/how to use them?
    - ssh key(pair)s are a way to make sure that remote computers can identify you (or your computer) securely. A pair is composed by a private part and a public part, which are generated together by a program called `ssh-keygen`. The private part stays on your computer and should never be moved or published anywhere, while the public one can be given to any service/host that needs to identify you. This includes GitHub, GitLab servers, HPC systems and so on.

59. Also, could you advise WSL user to be aware where they save their local repositories? I learned the hard way that you need to be mindful about saving inside or outside WSL folders 🥲
    - If you use WSL, be sure to work inside its folders to improve git performance and avoid interpreters and dependencies conflicts (mostly for VS Code users). Another interesting tool is using Codespaces, inside GitHub, which makes a container for your project, thus giving you control over dependencies and resources you need.

60. May I add here, few questions evolve around ssh-keygen. I think, the preferred method are now tokens, which you generate on the github page, and they can expire.
    - tokens are like passwords, specific for the service that you generated it at. YOu can use instead ssh keys in different ways - A ssh key identifies your computer/user, while the token is specific to the service, in addition to the user.

61. Can you give recommendations (advantages/disadvantages) for using python files vs. Jupyter Notebooks regarding vscode and github?
    - python files can be kept under version control and managed/viewed easily. With jupyter notebooks some additional tooling is necessary, otherwise the diffs, for example, are basically unreadable.

62. At the moment I see no disadvantage of using codium over vs code. Is there any?
    - There might be some extensions that rely on the telemetry features of VSCode, but apart from that they should be completely identical and thus one could argue that VSCodium is nicer as it won't spy on you.
        - Thanks!


## Practical advice
https://coderefinery.github.io/git-intro/level/

Don't know how to name your commit messages? https://www.conventionalcommits.org/en/v1.0.0/

- What about git add/commit -p?
  - it's a way to add/commit only a part of the code... (-p stands for --patch)
- But you also said you sometimes work with collaborators who don't use GitHub and you have to do version control yourself. That could include working with Word docs, PDF's coming from the collaborator, yes?

- can something be permanently removed from git history/github?
   - let's start with permanently removing from git history: yes: for instance
     with an "interactive rebase" you can delete commits, re-order commits,
     squash commits, rename commits ...
   - the same thing holds for git repos on github but note that public repos get automatically archived to services like https://www.softwareheritage.org/ so if I notice a big problem which has been in a public repo for a while and I remove it, you might still find it somewhere else on the internet

* WSL = Windows Subsystem for Linux, not surfaces!
* When you run WSL you can find the files in a "Linux" section on your file explorer, with the characteristic Linux penguin as an icon. (If you don't want to find everything using command line). Also to get to your Windows files within wsl you can navigate to /mnt/C/ etc., easy to move and access files between WSL and Windows.


## News for day 2 / preparation for day 3
- We went over what was in the schedule.  We demonstrated some in command line and some in vscode, but both work for the future
- Tomorrow, we do "git collaborative", which is putting all of the stuff we have done today together.  It's both an extension and practice of today.
- Even if today was hard, come back tomorrow for another perspective
- If you are planning to do the collaboration exercise **tomorrow** and are
  **not** part of team, please open an issue
  at https://github.com/cr-workshop-exercises/access-requests/issues/new?template=access-request.md
  (you don't have to write or edit the text there, just click the green
  'Create' button).


## Feedback

Today was (vote for all that apply):
- too fast:
- too slow: ooooooo
- right speed: oooooooo
- too slow sometimes, too fast other times: oooooo
- too advanced:
- too basic:
- right level: ooooooooooooooo
- I will use what I learned today: ooooooooooooooooo
- I would recommend today to others: ooooooooooooooooo
- I would not recommend today to others:

One good thing about today:
- It was good that we did similar tasks as the 1st day but locally so that we got deeper understanding.
- I liked getting some insights on more "advanced" git use cases like git bisect  +3
- Better stepwise guidance for the solution to git bisect, had to work backwards a little bit even with the solution. Step-by-step to revert the code directly to a branch with the last working commit might be good rather than an open-ended exploration.

- Great that I could follow the workshop even though I had another meeting today. Thanks for the flexible setup.

One thing to improve for next time:
- too much time for creating git repository exercises, it was possible to just follow along with the demo so I think less time or having an optional additional exercise we could try during that time would be  great +3
- I think a bit more explanation on the ways of pushing to GitHub (HTTPS/SSH, the credential options, etc. would have been helpful)

Any other feedback?
- I was a little lost on the git archeology exercise and was not able to solve it without solution in the terminal

General questions continued:
-  how can we verify if we are part of the team for collaborative exercise? Is this confirmed on registration or do we have an extra step?
    -  If you have accepted the invitation, then you are part of the team. Check your mailbox associated with the github account.

- You talked today about things to do and not to do. This is very helpful.
- However, when I started to use git I e.g. used different folders for different branches and also modified files remotely on github and locally at the same time - without committing:(. Now, I see this is not the way you would use git. Still I am afraid that I forget to pull the right branch in the beginning of my work, or put similar files with different versions in different branches and branch merges are hard in the end.
- To sum up, maybe you could specify a typical working routine like e.g. if possible to avoid confusion:
1. Thing to do git pull the right branch
2. change files and commit
3. push everything in the evening

- And also, would you recommend to change files only locally or only remotely on github to avoid confusions?
    - Change wherever is convenient, just remember on the local repository to commit and push when a change is done and pull before working on new changes.
    - I personally find it useful to do quick fixes (e.g. updating readme file) from the web interface. And more code-related work on the local computer.

- I would be interested in learning more about collaborating on code in a merge_request/new branch. Or if there are better options to collaborate.
    - We will do this tomorrow.

- If you enjoying using Overleaf and git, you might find this useful. In today's CodeRefinery workshop, I accidentally found that Overleaf can work perfectly with git. You can clone the overleaf project to your local computer, and then make modification, and commit, push back to Overleaf. Then the content on the Overleaf website would update just like how Github does.  You can do whatever you like in your local repository, like creating branches, merging, etc.. Overleaf only stores your master brach. In this way one can do version control of your paper perfectly without losing all the advantages of Overleaf. Also you can still work while overleaf is down.
