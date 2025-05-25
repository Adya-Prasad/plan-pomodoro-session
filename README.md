# R Package: Plan Pomodoro Session

```bash
install.packages("planPomodoroSession")
```
Plan and generate a Pomodoro schedule for your task, in a single step.

This function helps break your total available time into Pomodoro intervals: alternating focus sessions and breaks.
It is designed to be flexible and user-friendly by handling different input scenarios without throwing immediate errors.

## Steps To Create Your Own R Package
First, create a folder for your package project in **RStudio** and set it as a _set as working directory_ where we will use all commands in the console

1.

1. Install the `devtools` package
```
install.packages("devtools")
```
2. Load the `devtools` in your environment
```
library(devtools)
```
1. Install the `testthat` package, because we will use TDD, so we will write test cases first before the functions.
```bash
install.packages("usethis")
```
3. Load the package in your environment
```
library(usethis)
```
4. Now let's create a test preset folder, that will store all test files (This step may update your DESCRIPTION file too, you can check yours)
```
use_testthat()
# ✔ Setting active project to "/workspaces/125536957/r_pomodoro_project/project".
# ✔ Creating tests/testthat/.
# ✔ Writing tests/testthat.R.  - It will contains test dependencies and functions details
```
5. Now, start creating your test case files for each function
```bash
use_test("pomodoro_productive_ratio")
# ✔ Writing tests/testthat/test-pomodoro_productive_ratio.R.
# ☐ Modify tests/testthat/test-pomodoro_productive_ratio.R.

# Give the argument with the same file name that you will create for your function
# This command will create a file in the testthat folder inside the tests directory, and it will add `test-` at the front of your file name
# Use the same command multiple times if you have multiple functions and files. Each file for each function's file
```
7. Write your test cases code in test files. Check out this resource to write test cases with the test `test_that`.
8. Run the testcases, it should **fail** because you have not written any function yet.
```
devtools::test()
# ℹ Testing planPomodoroSession
# ✔ | F W  S  OK | Context
# ...
```
7. Now let's create the main function files to write our programs for the function. It will be created inside an `/R` folder. You can use the following command
```bash
use_r("pomodoro_productive_ratio")
✔ Creating R/.
☐ Modify R/pomodoro_productive_ratio.R.

# It will create R/ folder if it doesn't exist
# And a pomodoro_productive_ratio.R will be created inside that R/ folder
# Use this same command for multiple times for creating mutiple function's R with their name
```
8. Now write all functions correctly.
9. It's time to test our function, run the `devtools::test()` again and it should PASS all test, if not or if it fail please check your function and test cases and debug them
```
devtools::test()

══ Results ══════════════════════════════════════════════════════════════════════════
[ FAIL 0 | WARN 0 | SKIP 0 | PASS 8 ]
```
10. Since you wrote your functions and tested them, now make them available to use with `load_all()`
```
load_all()
ℹ Loading planPomodoroSession

# It will show loading your package. It will show the name that you write for your package name in the DESCRIPTION file.
```

11. Now let's check if your created function is loaded and ready to use. You can use `cat` command to check
```
cat(omodoro_productive_ratio(...))

# Use your function with correct arguments inside the cat, and your function should work accordingly.
```

12. Till now you created your test cases, functions, test your functions, and load & use your function, now you also need to create documentation manuals for your package. Documentations will be created inside the `man/` folder which stand for manuals. And documentation file should have `.Rd` extension and be written in **Markup language**.
```
devtools::document()

# It will create an empty man/ folder where you will create your documentation files
```
13. Let's create a documentation file
```
file.create("man/pomodoro_productive_ratio.Rd")
[1] TRUE

# It will create the file in the man/folder. Create a documentation file for each function.
```
Check out this resource to know How to write a documentation file

14. Load the documentation and check
```
devtools::document()
```
Check the specific documentation by using `?` before its name without its extension
```
?pomodoro_productive_ratio
```
It should render the documentation in the left panel (Please be careful)

15. Till now, we have created our test cases, functions, and documentation. It's time to build it. (Converting full source code into a single file)
  * We can use the `devtools::build` command in RStusio OR
  * R CMD Build in other IDE
15.1. Ensure your NAMESPACE file includes all function exports like this:

```
export(plan_pomodoro_session)
export(plan_pomodoro_session_custom)
export(pomodoro_productive_ratio)
```
15.2. After exporting the check and documentation, build check, build the package
```
devtools::build()

# [1] "a-path-before-your-working-directory/planPomodoroSession_1.0.tar.gz"
```
**_Congratulations!_** You have built your R package. This command builds and saves a `.tar.gz` (tarball) file, a directory ahead of the current working directory.


### 19. Let's use and test your own created package
19.1. Go to the directory where the `.tar.gz` file gets saved
install the saved tarball file (make sure you have installed `rtools`)
```
install.packages(path_to_file, repos = NULL, type="source")

# For example:
install.packages("D:/planPomodoroSession_1.0.tar.gz", repos = NULL, type = "source")
```
19.2. After installation, let load and use your package (library). Open your console, first load your library and start using your libaray's functions
```
library(planPomodoroSession)
```
now use your function
```
plan_pomodoro_session("Problem Solving", 210)
```
_It should work, if you are facing any error or issue, please revise the steps correctly_
