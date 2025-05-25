# R Package: Plan Pomodoro Session
```bash
install.packages("planPomodoroSession")
```
Plan and generate a Pomodoro schedules for your task, in a single step.

This function helps break your total available time into Pomodoro intervals: alternating focus sessions and breaks.
It is designed to be flexible and user-friendly by handling different input scenarios without throwing immediate errors.

## Steps To Create Your Own R Package

1. 
2. Install the `testthat` package, because we will use TDD, so we will write test cases first before the functions.
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
# ✔ Writing tests/testthat.R.
```
