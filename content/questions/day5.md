+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 5"
+++


## Icebreaker

- What do you want to be when you "grow up"?
    - veterinarian
    - become a scientist
    - Have cattle farms and milk products business
    - I'll say a funny one: streamer (who streams teaching/mentoring kind of stuff)
    - Baker (PhD to Bakery pipeline needs to be studied)
    - Employed
    - Retired and playing music and reading all the books I'm behind on

- How would you explain your current job to someone from the year 1700?
    - I analyze fancy paintings that show different diseases and try to improve medical treatment
    - Forcast the future
    - We ask the same questions to many people and see if different people answer differently (that's psychometrics in one sentence :D)
    - We try to make an assembly of bars and links walk like humans
    - Solve the causes of dark miasma
    - Provide machines that probably seem like magic to help the above people do those things

- What's the best documented project you have seen?
    - Deal.II
    - Numpy/scipy are pretty good overall.  Not fancy but somewhat reliable.
    - Ardupilot (Not the best documented, but the scale of the repository is impressive)
    - Klipper
    - Matlab - absolutely not
    - Tidyverse
    - "Best" is doing some heavy lifting here... maybe Julia's Tables.jl?


## Documentation
https://coderefinery.github.io/documentation/


- Is project documentation important? Why?
  - If you want anyone to use it... yes.
  - If no one is going to use it (not even yourself?)... perhaps not?
  - We forget things all the time, so it is important to document the steps.+1+1+1+1
  - I need at least a bare minimal documentation (like a readme) otherwise I will just forget what I was doing and what each script does... (and as a shell user, at the end of the day I often do `history > notes_for_dayDDMMYYYY.txt`)
  - Is important how to understand the rationale behind  the decisions , including how you choose to structure your folders (for example)
  - There are so many steps in the project that are stored only in your head initially. They must be written out once you step away from the project.


- How would you describe a useful documentation?
  - A good documentation need to be self-consistent. It should be understandable just by reading.
  - There is some balance/difference between "figure out new thing" and "I roughly know how it works. I need to scan and find info on one particular function quickly."  Different projects may specialize in one or the other

- How can you motivate your colleagues to contribute to the documentation?
  - (I like how there are no answers here...) Maybe try to make them proud of the work?
  - Learn to do a little bit at the right stages so that it doesn't seem like an artificial chore, and so that it minimizes the actual work (e.g. little comments when you start a script, or when you finish processing a data set).
  - Get them to also use it when learning?
  - Supervisor says it's important?

- How often do you write throw-away code?
  - Daily shell scripts are the typical throw-away code for me at least.
  - Depends how easy the code is, or if I am just testing and learning new stuff. But typically I right the steps on a journal when is related to the project, at least.
  - Weekly


## Motivation and wishlist
https://coderefinery.github.io/documentation/wishlist/

Documentaiton wishlist:

- Some working examples how to embedd the functions described. Just the functions does not help me very often
- Have a table of contents (if long)
- Avoid as much as possible ambiguous terms (e.g.: naming processes/folders/functions in a clear manner) .
- template input
- Search bar for specific functions or utilities
- Easy to make (focus on what's important, don't do a lot of other extra work)
- Some simple examples to get started (how fast can I get started?)
- Installation guide (e.g. pip, conda,...)
- Also state the dependencies and versions
- Easy to generate the document, the tool is important. i am using markdown for the documentation now, but would like to know more tools.
- Good quick reference (if I want to find info on one function, can I do this quickly?  I don't want to have to read through lots of text.)
- how this relates to possible publications (eg. where they are part of the code)
    - Also if they have certain citation wishes, if the code is used
- Description of all functions, their variables, output, purpose, with examples on usage and links to related functions

Questions continue:


## Popular tools and solutions
https://coderefinery.github.io/documentation/tools/

- What is difference between markdown and rST?
    - They are quite similar in principle.  Markdown is slightly more "easier HTML" and rST is slightly more "easier LaTeX" - but really, the base is exactly the same, the difference is only more advanced features.
    - MyST that is just mentioned basically unifies them
- But then how is markdown different from markup?
    - "markup" I think is just an abstract idea: way of labeling stuff.  Like "html markup"
    - "markdown" is one exact implementation of marking up text.  (Well, a whole family of similar things)
        - Oh. Then the choice of name is confusing....
        - yeah...


## In-code documentation
https://coderefinery.github.io/documentation/in-code-documentation/
(we do demos/Q&A, no exercises)

- But sometimes your comments in a script are more like a narrative, or even writing for yourself as you code...
  - yes
  - One funny thing a colleague once said is "in Python I don't need to have comments since the code says what it does".  Well yeah, every code theoreticalyl does that.  But narrative points/summaries/why things happen are still useful.
- very helpful is to keep track of the unit (like degree celsius instead of just degree), because this can make a huge difference, if you forget at one point
  - this could be done by using a proper variable name (e.g., 'temperature_C' instead of 'temperature_F', for example), or if one wants to be fancy, use different types
  -  yes and no, C and F could also refer to different measurements or different thermometers. While the unit is the most likely explanation for C and F it does not have to be.
  -  Also I find long variable names helpful and hard to read at the same time, so it is a weird trade off


## Writing good README files
https://coderefinery.github.io/documentation/writing-readme-files/

- I'm adding [!IMPORTANT] to Github README.md but it doesn't render.... It just shows '[!IMPORTANT]'
  - Did you use the `>` at the beginning of the line as well?
      - Oh, I see. Yes...
      - Does this render in general markdown, or only GitHub?


## Sphinx and markdown
https://coderefinery.github.io/documentation/sphinx/

- Why do you name the directory '_build' with a dash?
  - It's just sort of a convention in Sphinx, but not required (can be changed in the build scripts).  Sort of keeps "automatic/meta stuff" separate from "source stuff"
- I don't get where this sphinx directory is supposed to go relative to, say, a GitHub project directory or Python directory...
    - If this is part of another code project, we would often have it in docs/ sub-folder of the main git repo.  (docs/ is the place with all the sphinx files).
    - If it's only a sphinx project we usualy have the sphinx files at the root of the repository.
- Where is the unordered list? (Never mind, I didn't realize the sections were links)
- Will we go over the 'pin' appropriate sphinx version point made in the tutorial?
  - Where was this?  Is it about setting the version in the environment.yml / requirements.txt file/


### Deploy Sphinx documentation to GitHub Pages
https://coderefinery.github.io/documentation/gh_workflow/#exercise-deploy-sphinx-documentation-to-github-pages

- I don't get where I am supposed to create the `.github/workflows/documentation.yml` file in the repository (from web interface).
  - In the main directory of the repository (from the repository root, there is a directory `.github/workflows/`)
  - Ah I see.  from... Try the `+` icon on the file view.  It should give an option "create new file"
      - Under Add File? Yes (my screen was narrower so it was a plus).
      - So I created documentation.yml in the main directory of the repository. But when I go to https://github.com/USER/documentation-example/actions I am not sure what I should look for.
  - It should look like this: https://github.com/coderefinery/documentation/ (sorry for not being able to give more advice - ).  Except that the source isn't separated into a `content/` directory
      - Ok...
      - I'll try more when I get back
      - And the "Bring your own code" interactive session can also be a place to check this out together if you want to "debug it" live on zoom :) (no streaming in that case)

- Are there limitations to being able to use this with private repositories?
  - We think not (for in free repos)
  - I am not sure if the question refers to GitHub actions or GitHub pages, but just a reminder about [this warning](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#publishing-sources-for-github-pages-sites) from GitHub "GitHub Pages sites are publicly available on the internet, even if the repository for the site is private (if your plan or organization allows it). If you have sensitive data in your site's repository, you may want to remove the data before publishing. For more information, see About repositories." ...
  - ... so be careful that you do not accidentally publish some sensitive information (it shouldn't be stored in GitHub if it is truly sensitive)

- How can I easily see changes in Jupyter Notbooks or do I always have to covert them to .py files? Can you suggest a workflow here?
    - We'll go over this in the next session!

- Sometime a Jupyter Notbook is to long to be shown on gitlab? What can I do?
    - Hm.  My guess is that it is taking some time for the gitlab server to convert the .ipynb to .html.  This shouldn't be doing any serious computing, so I don't know what could slow it down.  My guess is server load/server resources
    - Personal opinion: if a notebook is too long, it is time to split it into separate parts.

- I have started to work with marimo notbooks, do you have some experience to work with them on github? I think the reactive part helps a lot to avoid mistakes in the code. However, when I do version control on github I would prefer jupyter Notebooks, as single cells and cell outputs can be seen. Adding the marimo "app" code to github is a bit confusing because each app.cell is a function with returns. Do you have recommendations or workflow suggestions for using the benefits of the two worlds: Jupyter and marimo on github?
    - I'm not very familiar with marimo and not sure if anyone here is.  We can look into it though.
- Can you please just share shortly the installation steps for jupyter lab? This is not accessbile at the moment (Conda environment for CodeRefinery workshops.).
  - https://coderefinery.github.io/installation/conda/ I am able to access it now
        - Thank you!

- is the git connection in Jupyter lab similar to git in VScode?

## Jupyter
https://coderefinery.github.io/jupyter/


## Motivation
https://coderefinery.github.io/jupyter/motivation/


## JupyterLab and notebook interface
https://coderefinery.github.io/jupyter/interface/


## A first computational notebook
https://coderefinery.github.io/jupyter/first-notebook/


## Notebooks and version control
https://coderefinery.github.io/jupyter/version-control/


## Sharing notebooks
https://coderefinery.github.io/jupyter/sharing/


## News for day X / preparation for day Y

- We covered the lessons as shown in the schedules.  All demos, you can do more later.
- Tomorrow we have: testing (practical, still a demo but has real exercises you can do later), and moduloar code development (this is a demo + discussion - you see ous go from Jupyter to a reusable program.  Very cool stuff.)
- Don't forget theo "bring your own code" sessions where you can get more help with your own work, or more Q&A on the lesson topics.


## Feedback

Today was (vote for all that apply):
- too fast: o
- too slow:
- right speed:
- too slow sometimes, too fast other times: oooooooo
- too advanced:
- too basic:
- right level: ooooo
- I will use what I learned today: ooooooo
- I would recommend today to others: oooo
- I would not recommend today to others: o

One good thing about today:
- The multitude of tools commented +1+1
- I appreciated learning how to do documentation, as I usually focus more on the code and writing comments within the code

One thing to improve for next time:
- I am missing some hands-on activity+1+1+1+1+1+1+1

Any other feedback?
- Thanks for today! Very useful material and tips +1+1+1+1
