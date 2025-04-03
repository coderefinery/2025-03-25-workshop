+++
template = "page-with-toc.html"
title = "Questions and notes from workshop day 6"
+++


## Icebreaker

### What programming language(s) are you normally working with:
- python: ooooooooooooooooo
- R: oooooooo
- C:
- C#:
- C++: oo
- Java: o
- Fortran:o
- Rust: o
- Julia:
- Javascript: oo
- Typescript: oo
- Matlab: oooooo
- ... (add if yours is missing)
- Natural language (ChatGPT ? :)): oo
- shell/bash: oooooooooo

### Whats the weather like at your place (and where is that)
- Sunny, some clouds, Espoo, FI +1+1
- sunny, Newcastle,UK +1
- Sunny in Helsinki +1
- Sunny, Bergen, Norway +1
- Sunny (Ulm, Germany)
- Sunny and windy, Greece
- Sunny, Taipei, Taiwan
- Sunny, Joensuu
- Sunny, The Netherlands
- Sunny, Freiburg, Germany

### What do you know now, that you wish someone had told you when you began [studies/research/work]?
- It's worth caring about the technical qualities of your work, since that is most likely to help your future career
- It will improve, eventually
- Packaging your code will save you time in the long run
- Writing test cases is part of the software development process
- The concept of unit test
- Organising my projects and codes will save me time in the future.
- it would have been easier to rewrite the uncommented undocumented code than to try to figure out how to do this after the fact
- it is so worth it to start a private git repo for your work, even very elementary burgeoning work


## Discussion: What’s easy and hard to test?

- 95%+ code coverage is hard on complex and legacy code
- Hard: Functions/ models you want to work with very large datasets where you need many variables
- Testing if students generate the correct R figure
- It is hard to take time to implement tests in your coding routine.
- generally hard if you don't have modualr code


## Testing locally https://coderefinery.github.io/testing/locally/#testing-locally

-  What if my test function has errors?
    -  Running the test reveals them :) If you find an error you often need to check both the code and the test.
- What is required in the test function to be tested by pytest? e.g. assert?
    - Pytest will run functions that start with "test_". They don't need to have asserts, but those are usually added to check for specific results. Without asserts, you are still testing if the code runs without errors.
- What would be a good alternative for pytest when using R?
    - I have never used it but it seems that this package is quite close to pytest https://cran.r-project.org/web/packages/testthat/index.html (my R use is just calling other people's functions so not much testing needed)


## Automated testing
https://coderefinery.github.io/testing/continuous-integration/

- a bit fast, should we do the exercise in parallel with you?
    - We're not giving enough time, so I would watch and try to understand, and do in the afternoon while reading/watching the material.
    - Yes, please follow along.
- How often do you use automated testing?  When do you add it?
    - If I publish the code, I try to add tests that cover the most important functions. But my recommendation would be to do it from the beginning, whenever your code has functions :)
    - Depends on what I'm planning to do. If it's something that will become a library, test everything from the beginning. If it's just playing around with things, I will not test that much.


## Test design
https://coderefinery.github.io/testing/test-design/

- How complete do you usually make tests - what do you find practical?
    - Depends again on whee, not everything needs to be tested necessarily, but especially for things where I want to make sure that I don't get "nonsense" I would make sure that the functio gives the right error (Concept of better failing than getting invalid outputs).
- If the code will raise an error/quit if an certain error condition happens, do you usually make a test for it or consider "I'll see it when it comes?"
    - Depends on how important the error is and how expected it is to get this and / or if it is handled in the code. If It's a "runtime error": no, but if it's an error I want to make sure is thrown (because I handle that kind of error in an enclosing function) than yes.
- Do you ever make tests to see what the function actually does, and develop code+tests together?
    - This works and I some times do this. But usually, I would check what the code actually does in Jupyter and then move the function to tests once I've figured it out.
- .split() splits on whitespace by default, so for `AAAAA` returns the same thing.  `AAA` is not in the list [`AAAAA`].
- "r" is missing in "occurence" in def test_count_word_occurence_in_string():. This is why the error said "count_word_occurence_in_sring is not defined"
    - Oh good catch!
- How often do you make end-to-end tests in scientific code?
    - I often modify someone else's code. In that case, I make an end-to-end test to make sure I don't break anything.
    - I think most codes should have some full end-to-end tests. They prevent a lot of problems in the long run.
    - Not as ofte as I should...
    - A good rule of thumb: When you fix a bug, you also have time to add a test that checks that function / part of the code. For end to end tests, if you notice a problem in untested code, it's probably time to add a test that runs the full code.


## Modular code development
https://coderefinery.github.io/modular-type-along/


### Starting questions

A. What does "modular code development" mean for you?
 - Different pieces are usabel separately and/or separatable.  Somehow organized in abstraction layers (like say, network stacks, ...).  Should abstraction layer concepts be taught more?
 - Split up code into different ideas
 - create bits of code that can work independently to solve a task
 - having different functionalities separated within the same file (methods, classes) or different files. They can be interconnected, but still independent somehow


B. What best practices can you recommend to arrive at well structured, modular code in your favourite programming language?
 - Think about it.  Functions/modules.  Try to make it like a library if if is relevant.
 - my favorite language is python, so overall, I try to follow pep8 to make it easy for others to contribute/use the code
 - In Python, always tryto have a "main" function that gets run with the `if __name__ ='__main__'`.  When I don't do this I have usually regreted it.
     - Why is that? A script will run when you call it from the command line.
     - Because too often, I've wanted to extend it later and call it from other code.  Then I need major rearrangements that would have been easier earlier.  (If I never get to that point, yeah, it doesn't matter)
         - Can you explain the benefit of having the main function? You can, after all, import a script and its contents into another using the `import xxx.py` command.
 - plan in advance, think a bit ahead even for small or trivial scripts (will you reuse it in the future? could it be useful for someone else or as part of something else?). That said, don't overthink it either, this can be a rabbit hole.
- Think of minimum good parts that might be reused.  Put them into separate functions/modules that are easy to test.  Combine that with your "hackish code" to solve your immediate problem.
- adding (simple, useful) comments from the beginning usually helps to structure things too, and helps to figure out missing parts or future developments.


C. What do you know now about programming that you wish somebody told you earlier?
 - if you are going to change something in the code, do it in a copy version of it and also start simple is not a bad thing, you can extend what you've created after
 - About making proper libraries, however your chosen language does it.
 - version control is useful and easy! You can do it just for yourself in your messiest scripts and will save you a lot of time.
 - Use an IDE/editor with color coding, syntax suggestions and checkers, but also don't use a huge IDE that doesn't feel light and ready to use for everything.


### Additional questions

D. Do you design a new code project on paper before coding? Discuss pros and cons.
 - It depends on the code. If it is simple or straightforward (meaning linear thinking is enough), I usually write a code structure as comments (like a recipe) and then start adding the code itself. Otherwise, paper helps to draft the idea and it is sometimes the only way I have to grasp how to start building the code.
 - When I have done this, I have always been happy with the outcome.  Unfortunately I hardly ever do it.
 - Sometimes I do, when for example I want to follow design patterns, because i'm still working on fully grasping the concepts. The pros: helps to better visualize what I need to do; and the cons: it will consume time to do it


E. Do you build your code top-down (starting from the big picture) or bottom-up (starting from components)? Discuss pros and cons.
 - A bit of both perhaps?  Usually I try to connect top and bottom as quickly as possible and then for each new thing, start at top/bottom as necessary. +1+1
 - Bottom-up. I try to divide in small tasks and solve each task, then I assembly everything. If you can easy get distracted or overwhelmed like me, it is good to focus on each step. The bad part is that sometimes you need to backtrack and refactor previous tasks to optimized or fix a dependent future task/component.
 - .

F. Would you prefer your code to be 2x slower if it was easier to read and understand?
 - For most code yet, not the 5% of code that is time-critical.
 - It really depends on the application. +1
 - If optimization is not required, yes.


## Modular code task
https://coderefinery.github.io/modular-type-along/lesson/

Suggestions for improving the code:

- When do you go to modules?
- Split the loop from tdhe plotting. +1
- you could also create a function for the plotting, other for the reading/computation (or put everything in the same function). This could become a class, but isn't it going too far for such simple code?
- Remember not everyone watching knows Python (but I guess the principles apply everywhere?)
- in the `plot_data` function, I think `mean` should also be a parameter
- ~~I guess .show() tries to open a graphical window?~~  Oh yes .show() may clear the plot for the next one... from matplotlib documentation: "If you want an image file as well as a user interface window, use pyplot.savefig before pyplot.show."
- Should data be read once for each temperature or once for all?
- Command line interface? Specify input files and output files from outside the Python code.
- You could use a mean function from some other library, like numpy?
    - And make the function pluggable - throw in any function there.
    - Some thing I have somehow done before: from the command line, give the function name like `numpy.mean` and it automatically imports and uses that.  (be careful with security/bugs though...)
- we could add a test
- Can we get to command line parts (and related - git, tests, package, ...?)
- So you can use "r-" in plt.plot(temperatures, "r-") to plot a red line instead of plt.plot(temperatures, color="red", linestyle="-") ?
- Are there advantages to using `click` over `argparse`?
    - `click` is more modern, easier to use, but an external dependency.  If you are using other external dependencies, you may as well use this.
    - `argparse` is built in in case you want to make something that can run with no dependencies at all.
- It's almost break time
- What's the code that does it?
    - Hm... yeah.  I don't know.
- Working example test:
  ```python
   def test_plot_data():
       temperatures = read_data("tests/data/temperatures.csv")
       with tempfile.NamedTemporaryFile(delete=False) as tmp_file:
           tmp_file_name = f"{tmp_file.name}.png"
       plot_data(temperatures[0:25], tmp_file_name)
       with open(tmp_file_name, "rb") as test_output:
           with open("tests/data/25.png", "rb") as correct_output:
               data1 = test_output.read()
               data2 = correct_output.read()
               assert data1 ==  data2
  ```
  The issues during presentation were:
     - we are comparing binary data (hence need to open them in binary format)
     - matplotlib automatically adds a filename extension to the file, so we were opening the wrong file during comparison.


## Workshop outro
https://github.com/coderefinery/workshop-outro/blob/master/README.md

- CATS
- https://coderefinery.zulipchat.com
- https://coderefinery.org/#newsletter


## News for day 6

- We covered the lessons as in the schedule
- The outro sesson went over future directions you can study if you want - recommend reading and/or watching.
- Don't forget the "bring your own code" session where you can come ask us - the instructors - about your own code or any follow-up questions.  Please register so we know how many might come and what topics to prepare.


## Feedback

Today was (vote for all that apply):
- too fast:
- too slow:
- right speed: ooooo
- too slow sometimes, too fast other times: ooo
- too advanced:
- too basic:
- right level: oooooo
- I will use what I learned today: oooo
- I would recommend today to others: ooooo
- I would not recommend today to others:

One good thing about today:
- Having parts of the lecture material also in my programming language (R ) made it easier for me to follow

One thing to improve for next time:
- ..

Any other feedback?
- This workshop is really helpful for me, thank you all. +1+1+1
- This workshop should be mandatory to students/researchers after their first programming course. It's better to start using version control as early as possible +1
- Really good initiative. Software development concepts are always welcome +1
- The collaborative notes were nice for interaction +1+1+1
- The kitty could be the course's mascot +1+1

General questions continued:
- Is the course material available online almost indefinitely in cases we neede them in future?
    - yes (with updates)
- To what email address do we need to send the documents to in order to receive a credit? I found this one: scip _@_ aalto.fi but it contains spaces, I assume this is not correct? Should it be scip@aalto.fi then?
    - adjust to removethe spam protection
    - yes

- Can we also get a certificate if we are no longer a student (as doctoral candidate or postdoc)? I would like to have a certificate for future job applications.
    - It says only people at a university.  Would you need it if you aren't?  I guess you can mail and ask.
    - I relayed to our chat to see if I get an answer quickly
