+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 1"
+++


## Icebreakers

Let's test the notes with some icebreakers! :icecream:


### Where are you connecting from? How is the weather there?

- Keilaniemi, Espoo, Finland! Cloudy... +4
- Helsinki - cloudy weather
- Germany, Karlsruhe - cloudy but warm enough :+8:
- Kuopio, Finland - cloudy +2
- Stockholm - also cloudy
- Bergen - Showering :+1:
- Turku, semi cloudy
- South Germany - a bit warm
- Helsinki - gray
- Lille - always cloudy
- Gothenburg - rainy
- Espoo cloudy :+1:
- Lund - cloudy
- Germany, Ulm - cloudy
- FI, Joensuu - rainy
- Netherlands, Delft - cloudy
- Ulm, Germany - cloudy
- Jülich, Germany - cloudy
- Bergen, Norway - shitty as usual..
- Helsinki, Finland - it is what it is
- Tampere, Finland
- Copenhagen, Denmark - cloudy
- Amsterdam, Netherlands - cloudy
- Espoo, Finland - cloudy
- Netherlands, cloudy
- Newcastle, UK cloudy
- Karlsruhe, Germany, Partly cloudy
- Paris, France, cold and cloudy
- Bergen, Norway, rainy and cloudy
- Helsinki, ugly gray
- Helsinki, baby
- Marburg, Germany, sunny (surprisingly)
- Galway, Ireland, rainy (of course)
- Paris :: cloudy
- Saeb, The Netherlands, cloudy
- Pavia, Italy, sunny :sunny:o
- Heidelberg, Germany - cloudy
- Stuttgart, Germany - cloudy but warm
- Helsinki, Finland - cloudy
- Singapore Cloudy
- Taipei, Taiwan - Sunny
- Karlsruhe, Germany, Partly cloudy
- Helsinki, cloudy
- Thessaloniki, Greece, cloudy :)
- Freiburg, Germany - sunny
- Rovereto, Italy - cloudy


### Have you ever wished you had a "code" time-machine to travel back in time?

*Poll: Add an 'o' to the answer that applies to you*

- Yes: oooooooooooooooooooooooooooooooooooooooooo
- No: oooooooo
- Not sure


## Intro to the workshop

Materials for the intro with links: https://github.com/coderefinery/workshop-intro/blob/master/livestream.md

1. How to set up directory that you mentioned?
    - This is sort of part of the "shell crash course" part.  But don't worry, we'll talk more about this when we get to it, it's only for day 2.
    - If you refer to https://github.com/coderefinery/workshop-intro/blob/master/livestream.md#own-course-directory, then the idea is just that you create a place where you store everything regarding this course, so that it is easy to find it afterwards. Any reasonable directory setup would work, to this aim.

2. Everything seems okay

3. Will a recording of the stream be uploaded later?
    - Yes, Twitch stores immediately (for 7 days), usually videos fully finalized and on youtube by midnight Finland time.  But no promises, we are only human
    - One of the benefits of the livestream format.


## Intro to version control
https://coderefinery.github.io/git-intro/

4. Is OneDrive a recommended place to store github directory?
    - It should not matter, although onedrive does also provide a mechanism to share files, which is redundant if you are using github. But it should be fine.
    - You would commonly use a local directory (or a network mount) but in the end, git just adds it's data to whichever folder  you choose (as long as it can use this like a normal folder)
    - If I may add my personal opinion, doing the old fashioned way ´git push´ on github is better. [here](https://dustinbriles.com/onedrive-and-git-dont-do-it/) some arguments.
    - When git is on a "network/cloud" storage system, it can feel slower in my experience. :+1:

5. Can we also have a training about how to store and organize data in near future? like, BIDS-MNE, HDF5, etc?
    - Just my opinion: HDF5 is a general-purpose data storage format, which is important to use especially for large datasets. BIDS looks specific to neurosciences ("B" standing for "Brain"). How much interest there is? I can see how a HDF5 would be interesting to a big audience though.
      For general data organization principles, though, courses in the second week should cover some good principles.
    - We are happy to accept suggestions for new trainings! -> support@coderefinery.org or scip@aalto.fi or training@nris.no.

6. Happy to have you guys :heart_eyes_cat:

7. I there limit in the size of the file or doc?
   - In principle not, but it is better to manage with git relatively small files. Although, there are tools to manage large files (especially binary ones). Typically you store *code* in a git repo, but not data files (especially, not huge ones), unless it is really important. For versioning data files, other tools/services might be more appropriate.
   - Oh I see, I have tried large data before but zip
    - External sites that remotely host your git repository (e.g. GitHub) have limits (100MB for GitHub [[ref](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github)])

8. Can we have the notes open on our side in parallel (ntoes that presenter is showing in live stream)?
   - Yes, this is recommended. At the beginning of this document is a recommendation of how to configure hour screen
    - This is the link that has been shown https://coderefinery.github.io/git-intro/ (linked also from the course schedule)

9. Can we use git for Word and Powperpoint? I thought it is only for codes.
    - It is technically possible, as git does not limit types of files it can handle. You won't get the full benefits of git though, as you won't for example get pretty diffs of things you have changed.

10. Difference between Github and Gitlab?
    - They are both services that provide a web interface to manage repositories. They have some subtle differences in the way that collaboration is managed (which might become clear later). A key difference is that there's only one GitHub instance, while many institutes/universities have the possibility to host their own GitLab instance where they can store code privately. But they provide essentially the same basic/intermediate functionality (meaning it's typically easy to map a feature of GitHub into a feature of GitLab and vice-versa, and what you learn about GitHub can be transferred to GitLab quite easily).
    - When it comes to the "social" aspect of coding (having others to contribute to your repository or you being able to contribute to others') GitHub (Microsoft) has become the standard, just because everyone is there. It's a bit like a social media that you do not really like, but are still there because your friends are there.
    - Aside, but not too far: Note that, although it adds a bit of complexity, it is possible to copy a git repository between GitHub and GitLab and vice versa. This reduces the risk of getting locked into a platform.


## Copy and browse an existing project
https://coderefinery.github.io/git-intro/browsing/

11. When we want to make changes in the repo, we do it in the forked repo, not the original one, right?
    - Yes, very likely if you try to do the changes in the original repository you will not have the permissions. We will talk later about how to contribute your changes back to the original repo, which is, after all, the final goal (in many cases)

12. Will we do exercise ourselves?
     - Yes, see the info above or follow the [exercise](https://coderefinery.github.io/git-intro/browsing/#exercise)

13. What's the difference between forking and cloning? Like when I am cloning, am I creating my own copy or not? Thanks
    - Forking means: clone this repository, but *on GitHub*. Cloning is a more basic operation, that means to copy a repository, and it can happen on GitHub (that's a fork), or on your computer. You can even clone repositories from your computer to your computer (in different directories...)... but that's typically not very useful (although sometimes it can be)
        - Thanks! Let's say I have a repository, and others are using it. I'd like to create a version which I will modify, while others can use 'stable' one. Is creating a fork and 'dev' repository (right next to the original one) a valid strategy?
            - This is possible, but using branches is a more "lightweight" approach - and branches will be discussed later in the course. Branches are the "killer feature" of Git
            - I would prefer to create a branch and work on it rather than having a new repository, more on this you will learn these two days

14. When I fork the document in the online GitHub, it doesn't automatically appear in my Desktop app? Should it? Do people usually use the Desktop app or the online GitHub?
    >> I had to go to "file" > "clone repository" in the desktop app, and there it appeared, so I had to clone it into my laptop manually. So when you fork things online, they are not automatically saved to your computer.
    >> It seems that if I edit something in the Desktop app, I will also need to "commit" and "push" for it to appear in the Web interface.
    - Hm, good question.  We've only prepared the instructions for the web interface, so it may be safest to use that.  If you figure things out, let us kno
    - You may need to somehow force it to sync (could it be called "pull" or "fetch"?  Though that may be something else).
    - While if might be convenient to use GitHub Desktop to interact with repositories on GitHub, it is slightly (although possible) less convenient to interact with other hosting services like GitLab, so what you do there might be slightly harder to transfer (*amended answer*)
    - Just to add to the previous answer, keep in mind that GitHub Desktop, until now, only has Windows and Mac versions. In case you will ever work in another system with Linux, then it is useful to already know how to work from the command line.

15. If the original repository you forked receives updates, are you notified in any way?
    - The page of your repository will show that your fork is "X commit behind" the original repository, and it will typically show a button "sync fork" that might be used to "pull" the changes from the original repo in your own repository. Although, things might not always go as smoothly... stay tuned for the rest

16. Does fork also apply in the other version control platforms? like gitlab ?.
    - yes , you can use fork on gitlab too. it has the same name fork on gitlab too.


17. is the cloned repisotory will be also updated simultaneously when i clone to my own repisotory during changes? so any changes imn the network graph viisble with commit? if i publish it back so it will also change the source so that person might get angry?
    - You can only push (send code back) where you have permissions, so you generally don't have to worry.  You can modify your own copy but it shouldn't affect anyone else.
      - Eventually, if you want to contribute back to the original project, there's a mechanic called Pull request... more on that later!
    - I don't fully understand the first part, but mostly in git there are commands to run to synchronize local + Github/Gitlab copies (push, pull, fetch).  Maybe you can make it do it automatically, but in my use I assume I have to run a command to sync.  But that's quick and automatic.
    - When you fork a repository, it is more or less equivalent to making a branch out of the original repo, without the possibility to merge. So your update should not interefere with the original repo, and you can contribute back to the main repo via pull request.

18. step 3 is not very clearn I could not find it? :/
    - I think "sides directory" means: from the main list of the repository, you can click on the directory named `sides`.  Then click on `guacamole.md` (basically, navigating to a single file view).  Then find the "History" button.

19. step 5 does not work, it says my repository is not indexed: Is this an intended response or a github problem I have to fix?
    - It's a feature of GitHub: to allow quick searches, they do some background processing beforehand (called indexing). You might need to wait for a bit, but searching should start to work again on its own.
    - You can also work around this for this exercise by doing the search in the original repository instead of in your fork: now that you haven't made any commits of your own yet, their contents should be identical for the purposes of this search.

20. What is the difference between forking a repo and a branch? Are they different words for the same thing or different activities?
     - They are different. Forking creates copy of the repository under your account on github. Branch creates a separate line of development within the same repository
     - Fork: You own the forked repository, you work on your own repos and submit a pull request to merge changes. Usecases: When contributing to an external repo you don’t have write access to.
     - Branch: When developing features within a repo you have access to.

21. step 5, i get this error This repository's code is being indexed right now. Try again in a few minutes.
    - See 19 above

22. step5 doesnt work for me i put it into the search bar with /salt and it says invalid name ...
    - I *think* it might be related to the indexing that takes a couple of minutes..

23. step 5 fails to me too "This repository's code is being indexed right now. Try again in a few minutes."
    - It takes a few minutes (less than 5 in my experience) - not sure?

24. 'We go to the main recipe book view'. i don't understand what is book view
    - It is "recipe-book repository" view.  (not a "book view") - book is part of the repository name.

25. ...In which tense is a commit message supposed to be? Past/present/present continuous? Or subjonctif? I'm asking this because it appears you do something and then commit not the other way around.
    - I think I've read imperitive (Do this and that.)  But in the end people do all sorts of things, most important to get something done.
    - Utilize the body to explain the "what" and "why" of the changes. To me that is most important. The purpose of commit message is to understand the changes
    - I think the best tense to use is the one where the verb is the shortest. One wants to convey as much useful information as possible using the smallest number of characters.

26. Step 5 wasn't working but after waiting it now works, the indexing was solved in less than five minutes. :cat:
    - Great!

27. what is the real meanign of blame: From a recipe view, change preview to “Blame” towards the top-left. To get the actual commit, click on the commit message. we can already see the commits from history? if i blame some line, then what happens: Blame prior to change 1fde064, made on Mar 5, 2024? pressing the button there
    - Yes you can see the previous commits from history. "Blame" (not the best term) is a git term to check who wrote each line of a file and when they wrote it.
    - Something fun: We once used "Blame" to see who wrote a line of code - 4 years ago - that breaks the app on production. Turns out it was our CTO, and beers were on him that day. :)
    - And of course it's not about "blaming", but about getting an idea about who did a certain change and with which commit so that, if you need, you can ask them for context, or just read the relevant commit message.

28. Can you explain in detail during the live session what commit, branch, master branch, etc are? I am not supposed to assume or take it as a given.
    - yes, the instructors will explain it on live
    - Also you can refer the [quick reference](https://coderefinery.github.io/git-intro/reference/)


29. I don't get step 5 working. It doesn't find anything. Could you show that during the lesson.
    - Hopefully it will work in less than 5 minutes!

30. In case you perform multiple (and different) changes to sections of a block of code, how do you set the commit message? or you have to perform one small change at a time and then commit?
    - You can write a broad commit message saying the overall theme
    - Sometimes when I do a lot and know no one will ever care about details, I'll write "daily work" or some such
    - In the end, it's up to you: decide what's useful for you + the project.  Bigger projects will have more standards (smaller commits, one thing at a time).
    - (My opinion) In principle: the role of version control is not just bein a rewind/reply button, but to have "snapshots" of files/functions/whatever that are supposed to work together, to be compatible. In a commit, you should typically add different changes together that are logically connected.
    - When you get more experienced, you will also be able to pick only some changes from the big bunch of edits and create individual commits from them, if it feels worth the effort (it often is, but not always) or even to split already-made commits. But "perfect is the worst enemy of good" so no need to worry too much: if you forget to commit often, it's still better to commit rarely than to not commit at all. :+1:

31. Why is it called 'Blame'?
    - An older version control system called it "blame" to be funny: like you are seeing who to blame for a problem.  Unfortunately this has stuck.

32. is there standard licnece file i can use? should i contact with lawyer to create?
    - We'll talk about this more next week in "social coding!"  Some standard ones to recommend.
        - If you use github and create a repository there, it actually asks you whether you want to add a license and offers you a couple of options.
    - Licenses are not hard: it's collaborating with people with different aims and necessities, that can be hard.
    - It's very important to re-use existing licenses rather than writing new ones. There's many options out there. You can have a peak at the content of Day 4 afternoon.

33. Clarify again how one can see the summary of what is permitted and not permitted under a certain license file? I just saw from the live there some green check mark red cross outs. Is there a high-level summary option?
    - There are many licenses, each one with their own special aspects. Next week, the lesson about social coding should cover some of these in more detail (see question 32.)
    - If the license is a commonly used one, GitHub is often able to render a summary view similar to that seen in the stream. If available, you can see it when you open the license file in GitHub, e.g. https://github.com/cr-workshop-exercises/recipe-book/blob/main/LICENSE in the example repo

34. can people sue us if we clone their repisotory?
    - I believe Github terms of service say that public stuff can be cloned and examined (as you would expect for a "public" repository).
    - Licenses should say how you are allowed to use it beyond that.  It is always good to check!  I always pretend unlicensed code is not usable to be safe.
    - No you cannot be sued. This is from the GitHub terms of service: "If you set your pages and repositories to be viewed publicly, you grant each User of GitHub a nonexclusive, worldwide license to use, display, and perform Your Content through the GitHub Service and to reproduce Your Content solely on GitHub as permitted through GitHub's functionality (for example, through forking). " (https://docs.github.com/en/site-policy/github-terms/github-terms-of-service#5-license-grant-to-other-users)

35. can you explain more about the benifits or usage of issue?
    - We'll see more on day 3, but yes!  Basically, if you want to coordinate what needs to be done, you can make a record there.  It helps to have it in one central place along with the code.
    - For example where we see problems in this lesson material, we make an issue and we'll remember for next time.  Someone can claim the issue and work on it.
    - You can also refer to issues within commit messages, and this might help keeping commit messages informative without having to write a lot in them.
    - It is also a good way to navigate to the "solution" of the "issue". Typically, once an issue is closed (resolved), there will be a commit referencing the code developed to solve it.

36. Is commit similar to push?
    - It is, typically, the "step before" push. Commits are typically done locally on your computer (not in this lesson, where we do it directly on GitHub, which is the remote repository), maybe one can do more than one commit before pushing them all together. Here, in this lesson, we are committing directly on the "remote" repository that lives on GitHub, so we do not need to push. When we modify files locally on our laptops, we need to make local commits and then with "push" we can "publish" them on the remote repository (i.e., GitHub)
        - Essentially push tries to put it on a remote place, while commit is for you local copy. So if there are changes on the remote, commit will work, but push will complain, that there are changes that are not reflected locally, at which point you need to reconcile the differences (merge/rebase).

37. What is the best practice about branches? Can we have multiple branches and how people usually decide when to create a new branch?
    - You can have multiple branches. Using structured branching strategy helps team collaborates effectively. Each branch having a single purpose is recommended and *merge frequently* (This avoids conflicts and merging smoother).
    - branching is a complex topic! "Modern" approaches put a stress on having as few *active* branches as possible, merging often into the main branch, but typically this requires automated tests to make sure you're not breaking anything (see automated testing lesson next week). An approach that recommends this is "Continuous Integration". Other approaches, where someone needs to keep actively developing/supporting different versions of a software at the same time, require more complex branching strategies (e.g., "Git Flow")

38. How to create a folder in github? instead of a file
    - You can create a file in a new folder by adding the foldername to the filename in the box, eg instead of "myfile.txt" you put "my_new_directory/myfile.txt", then it will create the new file in a new folder (when you pres '/', the directory gets separated from the actual file name)
    - For a folder alone: under the hood Git only tracks files.  You can't have an empty folder with a file.


## Commiting
https://coderefinery.github.io/git-intro/commits/

In this part: now we add our own commits to our copy of the recipe-book repository.

39. The Network visualization process is taking forever...
    - Yeah.. it has to compute stuff.  I wonder why it takes so long... it's not like it's a big repository.

40. which of the following option to chose? Commit directly to the new-recipe branch Create a new branch for this commit and start a pull request?
    - In step 2 we want to commit onto a new branch.  It says to make the new branch first, but you can also make it at the same time you make the commit (which is the saving)

41. why does it take so long to network graph will be loaded in the insight tab?
    - I don't know, it's always taken a while.  It doesn't seem like it should be so long... maybe it is because it tries to make the network across all forks?

42. at what time comign back again the lecture?
    - 12:00 CET (adjust this for your timezone)
    - After the time of this comment, the next time the clock reads xx:00

43. I can see now the changes other poeple made too in tht owner name but how to see my forks? i mean  we created new recipe outside of main branch so i could not see it in the netowkr graph? ah ok I see tit too but woith different color =)
    - Yeah, it should appear in the network graph (eventually...)

44. I just thought the same. When I looked under settings/general very much at the bottom, it was possible to detach the fork from the main branch. Is this a way to clean your own fork? However, I do not think this is intended for this exercise :D (Sorry for the mess, just realised this is better its own question than an answer to 43)

45. now i need to combine new recipe from fork and main brach?
    - Which step?  ("merging" is what we do after lunch)

46. (6) Compare the branches is not clear? where to write compare i dont get it
    - It gets added to the browser path.  Like https://github.com/USER/recipe-book/compare - you can copy and paste this into your browser, change`USER` to your username.

47. new-recipe had recent pushes 11 minutes ago comapre & pull request? should we press this green button?
    - We do this after lunch!
    - By clicking on the button, before actually creating the pull request, you can also see a comparison between the branches, but it is not exactly what you want to see here (you end in the `https://github.com/USER/recipe-book/compare` page, but you get a different kind of "diff" than you would like to see)

48. To compare two commits I had to open a new tab and copy/paste the respective hashes. What would be a more convienent way to do it?
    - There isn't a "simple" answer to this. there is the git-diff command, which essentially shows you a diff, but since I assme you want to have a comparison on a graphical user interface, the only other options are integrations into various IDE systems, where you can select different commits.
        - OK thank you

49. In the tag part of the exercise, I get: 'We weren’t able to create the release for you. Make sure you have a valid tag.'
    - What did you use as a tag name?
        - It works now, used the tag v1.0.0

50. could you clarify the base repository and head repository when I compare the changes in the lecture? which one to chose . i WANT TO SEE  the changes i made in the main and new recipe from fork and i want to see both of them but those two concept confused me
    - Oh good question.  "base repository" is like the upstream (central one we made).  "head" is the one you are working on (yours).  I think these terms are usually used within pull requests though, which we aren't getting to yet.
    - Which step are you on?

51. Following the /compare-trick above, one can compare commits on GitHub by adjusting the following URL: https://github.com/USER/recipe-book/compare/VERSION1..VERSION2 any example? I dont have version now (I only have a new recipe and main bracnh which has changes)
    - I think you can use the branch names (`main`, `new-recipe`) for `VERSION1` and `VERSION2` but I haven't tested this.
    - You can also use the hash names like `abc1234` of the commits.
        - Could you maybe provide an example for this after lunch? Are the two dots ".." between the two hash names of the commits necessary?
        - Working example: https://github.com/USER/recipe-book/compare/0241b03...9ce4dce where you have two change `USER` to your username. The commit hashs are taken from the commit history. They are displayed to the right of each commit in the history
            -so two hash names just next to each other?
                - With three dots inbetween and the order matters. You compare the second commit to the first
                - Some nitpicking/details from [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-comparing-branches-in-pull-requests#three-dot-and-two-dot-git-diff-comparisons)
                    - 3 dots: compare the second commit to the common ancestor of both commits
                    - 2 dots: compare the 2 commits
                - thank you!
        - Two dots with complete hashes worked for me.

52. Earlier, some comments were made about GitHub recognizing .docx files as binary files. How about pushing .ipynb jupyter notebooks? does it recognize them in a way similar to .txt/.py or other script files? e.g. allowing for comparison on lines?
    - GitHub can show differences among Jupyter notebooks. See our lesson: https://coderefinery.github.io/jupyter/version-control/#comparing-jupyter-notebooks-on-github
    - And we talk about this next week in the Jupyter lesson!
    - In general git has "diff/merge" drivers, where you can extend the diff and merge to other file formats.  It's not quite as integrated but can work.  It works for .ipynb!

53. I just realized that my forked project is "public" by having a look into the network graph. So I cannot change my forked version to private because this project is owned by you, is this correct?
    - It is possible, but first you need to transform the fork into a standalon repository (Settings -> General -> scroll down to danger zone, Leave fork network). After that, stil under the "Danger Zone", click on "Change repository visibility" and make it private if you wish. But if you do this you mish the connection to the upstream repository, so any updates there may be in that repo you need to check them yourself.

54. Working in the new branch:
    - Why does my brach keep showing up under the main branch? I cannot work int. Everything I do goes into the main brach. Is it supposed to be like this?
    - Hm.  When the branch is first made it's under the main branch.  When you add a commit the new branch is a sub-branch of main.
    - In step (2) we view a branch, and then making a new commit goes to that.  We'll demonstrate.


55. I may have missed it. Will this "notes" be shared with us after the course? It contains very insigtful questions and answers. Thanks.
    - They get archived on the website ("permanently" - thus the not including names part.)

56. Why comparing same branches doesn't show anything? If a file is modified or a new file is made, I'd expect it to be shown there.
    - I am not sure I understand the question, but I'll try anyway: A "branch" in this case means "the last commit on that branch". Comparing a commit to itself will show nothing, because there are no differences (X - X = 0 for all X, so to speak?). If you want to see differences between "the same branch" but at different times, you need to specify the *commits* that you want to compare (`ab1234...`)

57. Inactive commit
    - Why commit changes is not active for the file that I added in the branch?
    - Good question.  It doesn't let you commit?  Could it be you are editing the upstream one, where you can't commit directly (it will try to have you commit to your copy)
    - It is working
    - If you do not have any changes to a file, then the 'commit changes' button is greyed out


58.  what is the difference between the code full SHA and shorter code? which should be used?
     - It's mostly about more characters making the combination of characters more likely to be unique: the long one is pretty much absolutely certainly going to be unique, while in theory it might be that taking just the first few characters will not. But in practice you can use the short version almost everywhere.

59. what is difference between commit and commitish?
    - Do you mean "commit hash".  The "commit" refers to the thing, "commit hash" is the indentifier of a commit that looks like 35dbca5415 etc.  Usually people use the terms interchangably.


## Merging changes
https://coderefinery.github.io/git-intro/merging/
We are now going to "merging" - the previous exercise is now connecting to the next part of the lesson.

60. Can we make a pull request from the new branch to the main branch of the original repository? Or is it better to merge to our main branch before requesting the pull?
    - This is step (7) (optional) - and what we do on day 3.  We recommend doing it in your own fork, so that you can merge it.  We won't go merging to the main repo yet.
        - What is the common practice in general?

61. Is it good to change directly on the main branch in practice?
    - In some situations yes. If some of the below apply, it might be better to use branches, but if not, then it might be that working with different branches will not benefit you much
        - you work on multiple features at a time
        - you need to keep track of a "working" state somewhere (in the main branch) and want to test potentially breaking things in others
        - you work with other people on the same code

62. What to do for the branch after doing the pull request? I mean shold I somehow delete the branch?
    - It is common that the pull request is not merged right away, but some comments/changes are requested.
    - After all the discussion has happened and everything is fine to be merged, the branch CAN be deleted usually safely. The only information that is is lost when merging a branch is that a given branch was pointing at a given commit, but the commit history will show that anyway. And deleting branches helps in keeping the repository tidy (it is easy to end up with a lot of unused/stale/forgotten branches otherwise.)

63. personally, I don't mind, but as I understood there was a separate repo for recording/streaming, but then network graph you showed, had actually the usernames of owners.
    - Yes, we understand.  We can't stop that, but it's why we have a non-recorded one as default and a recorded one people can optionally use.  We hope most people use the non-recorded one, but a few people volunteering as demonstrators is good too.
    - but are you sure the one shown was the 'resorded' one?
    - I'll make a note to check before publishing - thanks!  Did you see it as the wrong one?
    - I am not sure just saw the student names and thought to double -check. But again, I don't think it is an issue. Thanks! :)
    - I appeciate it.  Always good to check, we've tried hard to keep anything personal off the stream unless explitely wanted.

64. Do we need to remove the branch ? (6) Delete merged branches here or it hows just how to remove? no action? my new recpe is now merged to main barnch of mine. but i did not combine it with public one yet
    - Before deleting branches, first check whether they are merged. If you delete an un-merged branch, it will be difficult to find the commits that were on that branch. If you delete a merged branch, the commits are now also part of the branch where we have merged to.

65. At step 6, I did not get what we remove now?
    - which branch have you merged to main?
    - my new recipe is combined to my main branch now it looks good but I dont understand what we remove at step 6?
    - If you created a different branch and committed on it, then you have now a branch, that is *not* main, that you can delete. If instead you worked directly on branch *main*, then you do not have to do any merge (you do not need to do step 5.). What is the name of the branch you created previously?
    - I have brnach called "main" and "new-recipe". now new-recipe is combined with main now i have one branch i guess
       - You can check how many branches you have on the main page of your repository. Where you have 'main', you can have/select other branches there - if they were not deleted. it's in the drop down menu.
    - When you merge, the "new" branch gets updated, but the old one still technically exists and is unchanged.  (Thus the part about deleting it)
    - oh tnen, ui need to remove the new-recipe we dont neeed anymore? new-recipe  is comboined with main and new-recipe becomes useless?
       - Yes, at this stage all the work you made on new-recipe has been *merged* into the main branch, and the branch new-recipe can be deleted.
       - ok, this is the task in step 6 then
       - yes. But make sure you delete only the branches that have been merged!
        new-recipe lpi-techm Deleted now =)

66. What's the difference between `git switch` and `git checkout`?
    - `checkout` is old vocabulary. It was a bit problematic, as `checkout` did all kinds of different things: depending on context and usage, you could switch branches with it or you could restore the repo's content to an earlier state. Thus, `checkout` has been split into two commands: `switch` (for switching branches) and `restore` (for restoring an earlier state). You can still use `checkout` too though, if that's what you have gotten used to. Usage of `switch` and `checkout` is pretty similar but not quite identical when switching branches. If you encounter a `checkout` command and want to decipher it into `switch`, the command comparison table in this [StackOverflow answer](https://stackoverflow.com/a/70454786) describes most common use cases.
    - `switch` works only with branches as argument, `checkout` works with hashes, branch names, files, so it may be confusing

67. could you explain the tag part again? I get lost about the purpose of creating a tag.
    - A tag is a way to signal to everybody interested in usin your code that the commit related to that tag is "important" (it can be a release with a given version number, for example). Technically, tags are like branches, but branches can be updated when you commit on them, while tags cannot change.

68. .(7) Contribute to the original repository with a pull request does it means we need to merge our end resylt to the public branch?
    - When creating a pull request, you do not merge, but you request someone else who has the permissions to merge your changes to do it. In other words, a pull request is a request to other people who own a particular repository to "pull" your changes into their own repository. Creating a pull request is the way you have to "merge" in a repository where you do not have the permission to do so.
       - so cr_workshop(pubblickly available) needs to get our end result? step 7 means that we request diana to combine our contribution to the online public branc?
          - to the "main" branch, yes. Note that the main branch cr_workshop might not look exactly like the branch you are asking to pull from: it's a merge, meaning that they might have some changes that you do not have, and your changes will be integrated into those.
    -- lpi-tech wants to merge 4 commits into cr-workshop-exercises:main from lpi-tech:main   (so i did like this so diana can confirm it accept or reject)? trying to get what we are doing in step 7.

69. I can see that there is a "Restore branch" button. Do we have any information on how long this stays such that we can restore it anytime?
    - Hm.  This is a restore branch after merge, right?  There is a "revert" that undoes the merge and I think "restore" will bring back the deleted branch.
    - But for your main question: I don't know.  But all the history is still there, so you can always restore the old states, so I guess those buttons stay there.

70. Why is it called 'pull request' if we are metaphorically 'pushing' code to the repository?
    - The problem is that we are not allowed to exactly push. It's the others, the owner of that repository, that needs to *pull* instead.
    - The idea is you "push" to your fork. But then to get those pushed changed to a branch onto either another branch OR another repository alltogether you ask the maintainers of that repository to "pull" your changes into their codebase. In many larger projects the main (and often even the dev branch) cannot be directly pushed to, so you have to create a brach for your changes and request those changes to be pulled (or merged in case of gitlab) onto the target branch.

71. (above) but in that case, calling it a request to 'push' would still be more natural, yes? I don't see where 'pull' comes instead, and it is very confusing.
    - If we are asking someone else to incorporate our changes to their repo, to which we don't have write permissions, what happens is that I _push_ to my fork of the repo, and then ask the other repo's owners to _pull_ the changes from my fork into their original repo.
    - Ah, ok. That is more natural.
    - In other words: it does not make sense to ask someone to "push" some changes if those changes have been already made available somewhere public (e.g., their fork of a repository), because I can always pull from a public repository (technically, at least)

72. [name] wants to merge 4 commits into cr-workshop-exercises:main from [name]:main   (so i did like this so diana can confirm it accept or reject)? trying to get what we are doing in step 7.
    - It looks correct

73. Does GitHub have a space quota restriction for free accounts? Are there premium accounts? What will you recommrnd -- saving only code files (for a project) or saving the data files as well (these can be quite heavy). For instance, on working with Aalto's triton HPC? what will be the best thing to do?
    - Saving binary files of up to some MB is usually allowed in a repository, although it might be risky for some other reasons (it is very difficult to review the content of a large/binary file). For large data files, it might still make sense to have them under version control in some cases, but they can make the git repository very difficult to work with unless one uses some tools like git LFS (Large File Support). For *research data*, your institution should have some infrastructure where you can store such data (someone from Aalto might have better pointers)
    - GitHub has restrictions but if you have a valid university email you can apply for GitHub Education https://github.com/education which basically turns your account into a pro one for a couple of years (and then they ask if you still have a valid university email). On Aalto's triton HPC you can use GitHub, or GitLab, or other options that are useful for you or you collaborators, there are no Aalto specific recommendations. If your project is somewhat sensitive, Aalto's gitlab is a bit better than GitHub (storage in Finland and managed by Aalto admins), and for real sensitive cases do not use a web-based remote and instead use an Aalto Linux shell server for remote.

74. It looks like we can merge our branch to the upstream repo if we "fork" from upstream repo, does that mean our "main branch" is more like a new branch from upstream repo? So that's why we can see other people's "main branch". And if we just "clone" instead of "fork" from upstream repo, can we also merge new branch to upstream repo? I thought "clone" is more like creating a local copy.
    - Re: the first part: That is correct. Branches having the same name but on different repositories are, as a matter of fact, different branches, although Git knows that typically branches that have the same name in different repositories should "match" each other and can be synchronized when requested.
    - Cloning might need also, additionally, to fork, if we do not have the permission to work directly on the original repository. In that case, we would typically first fork, and then clone the fork on our local laptop.

75. What is the differece between the currently available verison controls and how to choose one?
    - Do you mean, between different version control systems? yes
        - A nice comparisons is available at https://en.wikipedia.org/wiki/Comparison_of_version-control_software. Back in the 90s early 2000 CVS/SVN were very popular. Then git came and became the de-facto standard.


## Resolving a conflict
https://coderefinery.github.io/git-intro/merging/#resolving-a-conflict-demonstration
This is a demo only

76. what a nice cat ^^
    Yay, cat! `<3`
    CAATTT!! 🐈

77. So for a conflict to arise, there should be different proposed changes in the very same line (identified by line-number or by context?) ?
    - It is by context. For example, if you insert a bunch of blank lines before a line of code, it will identify the blanks as new, but the code on line 50, and now on line 60, will not be identified as a change. BUT if you have large or complicated restructuring of a document/script/etc, it will more likely just flag the whole chunk as being changed, rather than individual lines.

78. How does it look like if your work in command line (using git for instance)? How can you check the conflit then?
    - The diff will be shown in text-only format, with `<<<<`and `====` and `>>>>` separating the different versions, and then you just edit the file so that the separators and other extra content is all gone and the file looks the way you want. You can see some examples in [GitHub docs](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line).

79. . do we get credits based on the current exercises? do wwe need send mail?
    - Please check detailed instructions here: https://coderefinery.github.io/2025-03-25-workshop/certificates/
    - If something is missing or unclear I can update that page.
    - And short answers to your questions are Yes and Yes :)

80. Can someone from Aalto provide some specific direction to the latter part of question 73? Thanks.
    - Sorry I thought 73 was about the cat. :)
    - I guess the other 73, our numbering is a bit of a mess right now D:
    - I will renumber, I replied the "original 73"

81. Are there pointers on using VS code on HPC systems?
    - At Aalto https://scicomp.aalto.fi/triton/apps/vscode/
    - At CSC https://docs.csc.fi/computing/webinterface/vscode/


## News for day 1 / preparation for day 2 (and 3)

- Recordings will be available immediately at the URL
  https://www.twitch.tv/coderefinery/videos when the streaming stops.
- There will be more "local" work tomorrow, if you plan to do the exercises
  please make sure you have a working git installation in your computer (e.g.
  with VS Code or with the shell terminal, see instructions at
  https://coderefinery.github.io/installation/).
- Day 3 is when we will collaborate together and we will send you detailed
  instructions on how to do that (


## Feedback

Today was (vote for all that apply):
- too fast: o
- too slow: ooo
- right speed: ooooooooooooo
- too slow sometimes, too fast other times: oooooo
- too advanced:
- too basic:
- right level: ooooooooooooooooooo
- I will use what I learned today: oooooooooooooooooooooo
- I would recommend today to others: ooooooooooooooooo
- I would not recommend today to others:

One good thing about today:
- Good number of breaks
- hands-on exercises
- Showing how to do stuff on stream helps with practice
    - +1+1
- Nice and clear. I attended two years ago and back then it was too fast and complicated. I had to stop after the second day
- Good speed. Nice to have exercises in between and also short explanation after. And good that we have breaks.
    - +1+1
- More interactive than I initially expected, I thought exercises are for the afternoons. I liked that

One thing to improve for next time:
- The time dedicated to exercises was sometimes a bit too long, regarding that we have the answers and there is a demonstration/explanation after.
    - +1 I agree, -1 I disagree :)
- Sometimes the activities were jumped into too quickly without explanation for why they were useful or important or why we needed to do them.
    - Second that
    - Give more time for demostration of steps, as sometimes it is confusing since we have different interface on our local computers
- It would be nicer if you try to solve every excercise.+1
- Some demonstrations it wasn't clear if they were "type-along" or we would have time to do the exercises after

Any other feedback?
- This format (Twitch + note-based feedback) works pretty well. IMO, it is better than Zoom + comment.
    - +1+1+1+1+1
- I will recommed this to my team. Should be compulsory for anyone working with data in our faculty
    - +1+1
- Over all, a great days. Thank you.
- Thank you for your time and I respect your way of teaching. Keep up the good work.
    o +1+1

General questions continued:
- For tomorrow, which one do you recommend: VS code-based or shell-based (and which shell, Git Bash?)? I am comfortable with both. Which one do you use?
    - Really, whatever you currently mostly use, since you are more likely to keep using it.  You can try both tracks and see how they compare - that's probably most useful for you.
