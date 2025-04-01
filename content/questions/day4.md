+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 4"
+++


## Icebreaker

- Heard/read any good April fools stories today (or in other years)?
    - Finnish forest ministry put up vending machines for selling authorization papers in the forests
    - April Fools Day is cancelled this year because no prank can top the reality going on right now.
    - Monster Hunter releases news about fake version.
    - Newspaper reported on the mysterious substance H2O (without calling it water), saying that it is dangerous to breath in, but at the same time crucial to our survival. They got a lot of worried mails after that

- Have you ever heard or said "It works on my computer"? What does this mean in practice? How did you solve it?
    - Yes.  Dig into code and spend *lots* of time to figure it out.
    - It probably means that the other person does not have his/her environment under control. solution: spend lots of time to show that person.


## Reproducible research
https://coderefinery.github.io/reproducible-research/


## Introduction - how it all connects
https://coderefinery.github.io/reproducible-research/intro/


## Motivation
https://coderefinery.github.io/reproducible-research/motivation/

**Questions to audience**
- What are your experiences re-running or adjusting a script or a figure you created few months ago?
    - Have to develop an webpage on top of someone else's code. Thankfully, the previous person was still on the project and could answered me maaaaany questions.
    - I ran simulations on a computational cluster and there the seed was generated differently than it was now in the software package. It took me a while to figure this out when I was asked to submit my code for a review.
    - When I switch from Python2.7 to Python3, I had to adapt all the prints in my codes. I also face issues when some libraries modify the syntax of some functions and I have to go back to older versions.
    - I usually find that my needs are now a little different so I start adjusting.
    - It used to be a hazzle, but when I started to write common figure configurations on the top (e.g linewidths and figure sizes) and section my matlab code (I can run them individually), I was able to do the figure components one after the other. For my thesis I ended up using tikz and importing the plots only as graphics, which is also more reproducible
    - Always make it reproducible, preferably one command.  If it takes to long, hopefully split into several stages (which still are documented).
- Have you continued working from a previous/another student's script/code/plot/notebook? What were the biggest challenges?
    - Mostly my code, and it's been less of a pain each time.
    - I did and I had a problem for example with "protein ids" not matching anymore the ones you could find online
    - I have been lucky enough to use codes written by experienced researchers, who have documented it well. Biggest problem --> software not functioning (different versions etc)
    - virtual environment was not working as expected
    - Requirements and setting up the environments.  Then, understanding enough to run it beyond what I was first told.
    - It was not running. Better to start anew...
    - Sometimes I find it is much easier to start from scratch than trying to understand the original code.+1
    - I mainly use my own codes.
    - Yes. I was thinking to move it from matlab to python, and I regret never doing so. It would have helped me understand it more in depth, because I have to copy it and at the same time the code would be more conform with my disciplines preferred coding language. Also plotting would be much easier.
    - I asked the person to explain the code to me and I started with their idea and copied only some defintions, but wrote a new script.

**Your questions and notes**
- When I was a younger researcher someone once advised me "never start with someone else's old code, always do small problems that you can start from scratch" - it was practical advice but sure means that we never get to bigger, harder problems.

- I have heard this "can't reproduce results after paper reviews" so many times.

- Spending a lot of time on making my research reproducible is not being valued by my superiors. They just want results. That makes it hard to justify why I am the only one taking more time than others...
  - I know!  (question to others: has anyone ever had a supervisor that valued long-term work?) Yes, but only if the supervisor had background in bioinformatics :)
  - I don't know what to do about this - any ideas?  I can only hope it gets better later.
  - I think it is your job as a researcher and will be valued by the research community

 - When you have sensible data (e.g. patient data), is it save to store it on GitHub? What are alternatives?
     - Code or actual data? If it is the latter, you should not use git for data, since github has a maximum folder size it lets you update (I wanted to do this with preliminary data in my Bachelor thesis and failed miserably :D).
    - Regarding the "safe" part: I believe it is not safe, but please correct me, if I am wrong


- How about using `make` to make a project completely reproducible (including re-running dependent part of the code, when we change some part of it?
    - OK, you were going to talk about it.
    - I find `make` a little cumbersome, I will try `snakemake`


## Organizing your projects
https://coderefinery.github.io/reproducible-research/organizing-projects/

**Questions to audience**

- How do you collaborate on writing academic papers?
    - These days most people I know seem to use overleaf. +1+1+1+1+1+1
    - google drive/docs... +1+1
    - I write most of the paper. At the beginning, I was doing it locally, but I moved to overleaf few years ago.
    - we use MS words for writing papers and onedrive for storing different versions.+1+1
    - Our university offers Overleaf licenses, but my colleagues prefer Word. So if I write a Latex document I always have to convert it in Word somehow for my collaborators comments.
        - You can comment pdfs, so maybe the can write their version into a comment and mark the line of text, instead of you going all the way to make it a word document?
- How do you handle collaborative issues e.g. conflicting changes?
    - discuss them and find the best wording/version
    - My collaborators send me comments and I implement them with an highlight font (bold, color).
    - Typically the main author was doing most of it, the others did changes, but the main author had the last word. If they were not sure, they would discuss it. +1+1
    - Yeah, usually one main person integrates it all


## Recording computational steps
https://coderefinery.github.io/reproducible-research/workflow-management/

- I am using snakemake to make my project analyses part reproducible, accessible etc. Are there any workshops, courses you would recommend to become more fluent in Snakemake? I know they have good documentation online with some tutorials etc but still would like to have some more practise with it.
  - There has been a training event recently https://training.pages.sigma2.no/tutorials/independent-jobs-in-parallel/,  Recording: https://www.youtube.com/watch?v=GRWysq3y7jM#t=1h13m31s, which might mean that there will be other editions in the future? Super. Great, thanks!


## Recording dependencies
https://coderefinery.github.io/reproducible-research/dependencies/

- Regarding the python environments, what is a good practice to when deleting an environment (after saving the .yml file)?

- I just recently learned about pyproject.toml files -> they are great. They let you set up your venv with a single file. it also offers to write extras like a "debug" setting, that also installs pytest or coverage, while the main configuration does not --> yes, i just learned about uv, which is suppose to be a good tool for those .toml files
- .

https://coderefinery.github.io/reproducible-research/dependencies/#demo
- Which version do you expect to be easiest to re-run? Why?
- What problems do you anticipate in each solution?
    - A:
        - It is possible to miss some critical libraries.
        - Hard to know what is there, have to search the text, easy to forget
    - B:
        - Dependencies issues due to wrong version.
        - Incompatible versions, needs manual installation of each library
        - Not structured, can't automaticalyl act on this information and install
    - C:
        - Works if it is not too far in the past... Otherwise might get tricky to get it working
        - A recent version of the github projects can update the other libraries and create dependencies issues.
    - D:
        - This should already run fine, but tags can be deleted +1+1
        - Sometime it could be difficult to install certain versions of software. It will be nice to indicate which packages are more critical than others.
        - While this allows you to set it up, writing very defined versions may also be problematic if you miss important security updates in the packages.
        - You won't automatically update and notice problems.  Someday you realize you have to update it all at once.
        - If someone else needs to run this with some other version of one dependency, it will be incompatible.
    - E:
        - Seems to be the safest way to me.
        - Probably the safest.
        - This version seems better, because prioritize using conda pkgs (and their versions) and I think the pip installations should be done isolate (`pip install ...`)

- Did you explain what 'channels' are (where to download packages)?
  - Not yet!  Hopefully below
  - "channels" are a way for an person/organization to have their own distribution.  Package can have the same name in different channels, while in the main channels/PyPI there can only be one package with a given name.
  - It gives some responsibility for each package.

- What is the difference between Conda and Pip? It is recommended to install packages using conda first, then Pip. Are they installing the software in the same place?
  - pip: older, doesn't have special handling of compiled libraries.  So can have some problems for scientific code.
  - conda: designed specifically because installing all compiled the scientific libraries using pip was hard.  It contains everything, even C libraries.  So is more flexible
  - But conda has now the problem, that it has some very specific licences because it "anaconda" went corporate. It is free to use in an academic setting but I wrote my thesis at a company, where it is forbidden to use. There are still some conda channels free to use but not all of them
    - "anaconda" has a license problem, and also the default channels for "anaconda". That's why we suggest using miniforge, that offers a drop-in replacement for the 'conda' command/package manager, but uses 'conda-forge' as the default channel, completely ignoring the anaconda channel - so you're safe
    - Yes, very true.  But, that is "main" / "anaconda" channel specifically.  Not conda the package installer.  As long as you use the conda-forge channel, license is OK  (we've updated our docs for that)
    - I can tell you the company just banned it all to be safe
        - Ah I see.  Well, I understand the caution given all the problems they caused.  I guess pip has to stay...
        - Could you ask if you can install it via "miniforge" which disables the anaconda-licensed channels by default?

- I want to add here, that the best way for python virtualenv is not a txt file (even if it records dependencies) but instead using `pyproject.toml`, because it lets you automatically install the proper dependencies using `pip install -e`.

- Is there an alternative to Conda for managing C/C++ dependencies, especially one that allows using `sudo` for system-wide installation?
  - I have heard of some such things though CodeRefinery but I don't remember.
  - "conan (I never used it) or cmake (and this assumes that the user needs to compile something that depends on other C/C++ code.)"

- In which folder we should create conda environment?
  - I usually install miniforge in my home dierctories, the environment.yml files are tracked in the project repositories, and the environments made in the project dirs (and gitignored).
  - Environments can also be built/installed in home directory so kept separate from projects (this is default if you make them by name)

- I am confused what miniforge is, miniconda...
  - Oh yes those need to be clarified.  Two separate concepts:
      - What you download
      - Where the downloaded thing gets software
      - Either one *can* access all channels but defaults are different.
  - Anaconda: commercial distribution, including an installer for conda+default packages+GUI.
      - So the 'installer' means 'installs packages you specify'?
      - In this case it's "thing you download that installs the base.  And that base (through conda) installs other stuff you request"
  - conda: the open-source package manager
  - conda-forge: the channel that has a more open license.  (the channel itself is maintained by an open-source project)
  - miniconda: A mini downloadable installer that installs conda + Anaconda channels (the commercial ones)
  - miniforge: A mini downloadable installer that installs conda + conda-forge channel by default, and disables the commercial channels.
      - So this is a way to get rid of all the license issues with the Anaconda channel and thus why we recommend this.


**Questions to audience**

- Are you using any dependency and/or environment management tool in your work?
	- No: oooo
	    - why not?
		- no since I am always having difficulties with installing/managing different versions of software in cluster already at first place
		- I did not know about these possibilities.
	- Yes: ooooooooooooo
	    - which?
		- pip / virtualenv ooo
		- conda +3+1+1+1
		- micromamba +
		- whichever is instructed for a spesific package, usually pip or conda
- Have you heard about or been in contact with containers (docker, singularity, podman) in your work? How did you come across them?
	- No: ooooo+
	- Yes: ooooooooooo+1o
    - Maybe? Haven't heard the term container yet: o
    - Very preliminarily, but we want to bring containerization to our software engineering efforts for portability  (and also to maintain software with dependencies that are out of support life)


## Recording environments
https://coderefinery.github.io/reproducible-research/environments/

- Containers like food trucks?

- Just a general question. These tools and so on can be used regardless of the language that you code in?
  - About containers or everything today
  - about everything today
  - In general almost everything today has implementations in every language (and all the concepts are analogous), but you might need to see what is recommended in each language.  Now that you know, you can figure that out easily.

- Is it useful to create a container if we only using python? I would expect the python library and conda to work similarly on all the version of Ubuntu (for instance).
  - At least in my experience, yeah, I can usually make properly packaged Python stuff work wherever.  Well, wherever has a Python environment
  - If you don't have a dev environment wherever you are running or need to transport the dev environment (python, conda), maybe a container is worth it.
  - Example: in our secure data analysis platform, it's hard to even move files into the environment.  So, installing Python/conda + downloading from web is hard there.  It's recommend to make a container file, easy to move that one container file to the secure system.


## Bring your code session
https://coderefinery.github.io/reproducible-research/where-to-go/

-> Bring your code session (Wed (Apr 16) , 9:00 - 11:00 CEST), registered participants will get an e-mail with the details.  Come and ask personal advice from the instructors


## Social coding
https://coderefinery.github.io/social-coding/social-coding/

### Question 1: Why would I want to share my scripts/code/data?

**Choose many**. Vote by adding an `o` character:

- A: Easier to find and reproduce (scientific reproducibility)
  - votes:oooooooooooooooooo

- B: More trustworthy: others can verify correctness and find and report bugs
  - votes:ooooooooooooooooooo

- C: Enables others to build on top of your code
     (derivative work, provided the license allows it)
  - votes:oooooooooooooooooo

- D: Others can submit features/improvements
  - votes:oooooooooo

- E: Others can help fixing bugs
  - votes:ooooooooo

- F: Many tools and apps are free for open source, so no financial cost for this
     (GitHub, GitLab, Appveyor, Read the Docs)
  - votes:oooooooooooooo

- G: Good for your CV: you can show what you have built
  - votes:ooooooooooooo

- H: Discourages competitors. If others can't build on your work,
     they will make competing work
  - votes:

- I: When publicly shared, usually we time-stamp or set a version,
     so it is easier to refer to a specific version
  - votes:oooooo

- J: You can reuse your own code later after change of job or affiliation
  - votes:ooooooooooooooo

- K: It encourages me to code properly from the start
  - votes:ooooooooooooooo


### Question 2: The most concerning thing for me, If I share my software now

**Choose one**. Vote by adding an `o` character:

- A: It will be scooped (stolen) by someone else
  - votes:ooo

- B: It will expose my "ugly code"
  - votes:oooooooooooooooooo

- C: Others may find bugs and mistakes. What if the algorithm is wrong?
  - votes:ooooo

- D: I will get too many questions, I do not have time for that
  - votes:o

- E: Losing control over the direction of the project
  - votes:o

- F: Low quality copies will appear
  - votes:

- G: I won't be able to sell this later. Someone else will make money from it
  - votes: o

- H: It is too early, I am just prototyping, I will write version to distribute later
  - votes:oooooooooo

- I: Worried about licensing and legal matters, as they are very complicated
  - votes: ooooooooo

- (I put it in Jupyter Notebook format, that wasn't suitable for anyote to reuse it.  And never had time to update.)


### Question 3: Why is software often treated differently from papers?

Free-form answers:
- Science funders don't seem to care too much about code, more about papers +1+1
- often written by researchers without background in how to write readable code +1+1
- To evaluate software properly, another layer of quality assurance and testing would be needed. Researchers are already overwhelmed with all the other roles. Maybe publishers and funders are not interested in investing on people to do the job.
- Code becomes useless when the paper is published, except for others to reproduce the results.
- Hard to keep it future-proofed and functional, while papers are eternal; maintenance isn't funded +1+1
- The previous generation treated it different and they are deciding things now
- ...


### Question 4: When you find a repository with code/library you would like to reuse, what are the things you look at to decide whether you use it?

Free-form answers:
- How easy it is to use it +1+1+1+1+1+1+1+1+1+1+1
- How fit-for-purpose it is for my project +1+1+1+1+1+1+1
- If others have already applied the code successfully and given it a good review +1+1
- How concise, coherent and relevant the documentation is +1+1+1+1+1+1
- How good the documentation is and if there are examples that appear relevant for my field +1+1+1+1+1
- Does it appear to be actively maintained +1+1
- A quick overview: does it look like the authors cared about it relative to its value?
- does it have a license? If it doesn't, it can be problematic if I want to modify it or reuse it as part of my own workflow. Similar troubles if the license is too restrictive.+1


continued:

- If you bring code without a license, in practice no one will really care if you keep using it (whether or not that's technically correct).  But then if you need to share a *new* version, you can't!  You are working on effectively "dead" code.


## Software licensing
https://coderefinery.github.io/social-coding/software-licensing/

**Question to audience**
#### Question 5: Which of these are derivative works?

**Choose many**. Vote by adding an `o` character:

- A. Download some code from a website and add on to it
  - votes: oooooooooooooooooo

- B. Download some code and use one of the functions in your code
  - votes:ooooo

- C. Changing code you got from somewhere
  - votes:ooooooooooooooo

- D. Extending code you got from somewhere
  - votes:ooooooooooooooooo

- E. Completely rewriting code you got from somewhere
  - votes:oo

- F. Rewriting code to a different programming language
  - votes:oooooooooooooo

- G. Linking to libraries (static or dynamic), plug-ins, and drivers
  - votes:ooo

- H. Clean room design (somebody explains you the code but you have never seen it)
  - votes:

- I. You read a paper, understand algorithm, write own code
  - votes:


- Can you please put the answers below these questions, for later reference?
    - Usually we have solutions in the materials (see "solutions") here: https://coderefinery.github.io/social-coding/software-licensing/#exercise-derivative-work
    - Yes, but the answers in the live stream are much more detailed and somehow contradict the solution (depending on the situation)
        - Thanks for the feedback, we will look into updating the materials. You may also refer to the recording for later reference
        - Funny thing is somehow that's realistic, you get different answers depending on who you ask... it's a big problem that everything is so unclear

- Is static library linking a derivitve work?
  - GNU project would say yes (with the GPL)
  - But a lawyer would say "it's up to the courts to decide on a case-by-case basis".  It would depend on how closely linked it is.  For example if something is made exclusively to use on library and won't work without.  vs.
  - The idea is that if you link statically and then distribute the binaries you are including machine code that was generated from code written by someone else.
  - For example this says there is ambiguity depending on the case, it can probably be a law students thesis by itself: https://en.wikipedia.org/wiki/GNU_General_Public_License#Linking_and_derived_works

- I want to take licensing into account, but I do not know where to mention the source code in my work. The README? The LICENSE? Somewhere else?
  - Normally get a copy of the license and add to file LICENSE. I might mention it in the readme also
  - A lawyer would say "include a header at the top of every single file" but in practice most don't do that unless you want to be very professional
  - Best advice I got was "if you find enough evidence that something has a license, you can assume it does and thus use it."

- If my code is based on an algorithm from a paper how would I go about citing the influence there?
    - You'd cite the paper (both in code, and in whatever publications used the code)
    - how do you correctly cite in code? Is ist at the beginning of the main file or just the function or class where you used it?


## News for day 4 / preparation for day 5

- Tomorrow continues like today: demos, discussion, Q&A.
- There is more you *can* do yourself if you install the software requirements (but we don't expect this, or give you time to do it).  Consider it like homework.
- Tomorrow's topics are: Documentation (including how to document the way we make our lessons) and Jupyter (focus on reproducibility and sharing)


## Feedback

Today was (vote for all that apply):
- too fast: o
- too slow:
- right speed: ooooooooo
- too slow sometimes, too fast other times:
- too advanced:
- too basic:
- right level: oo
- I will use what I learned today: oooooooo
- I would recommend today to others: ooo
- I would not recommend today to others:

One good thing about today:
- Licenses discussion +1
- overview over different tools available +1
- Clarifying how the license can be used is really helpful for me. +1
- Snakemake should be very useful.+1+1

One thing to improve for next time:
- The morning was a bit difficult to follow for me as a non-Python user.+1
    - Yep, we are sorry about that!  It's hard to speak in every language at once.  We hope you saw something you can study later for your own languages and can work on this in the future.
- Live audio seems not very good. I need to refresh every now and then. (I'm not sure this is only for me.)
  - Oh, anyone else have this problem?  I think I noticed audio missing once or so.  I'll check recordings.

Any other feedback?
- ..

General questions continued:
- ..
