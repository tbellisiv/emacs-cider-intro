# Running Tests

## Overview

CIDER provides support for running unit tests created using the Clojure [core.test](https://clojure.github.io/clojure/clojure.test-api.html) library. Tests can be executed from buffers containing Clojure application code, unit test code or from the CIDER REPL.

## Hands-On

Open the file `palindrome.clj` located in the `code/clj/cider-tour/src/cider-tour` directory of the GitHub project:

![palindrome_clj.jpg](images/palindrome_clj.jpg)

In another buffer or frame open the file `palindrome_test.clj` located in the `code/clj/cider-tour/test/cider-tour` directory of the GitHub project:

![palindrome_test_clj.jpg](images/palindrome_test_clj.jpg)

`palindrome_test.clj` contains the unit tests for functions defined in the `cider-tour.palindrome` namespace.

Now switch focus back to `palindrome.clj` and run all unit tests for the `cider-tour.palindrome` namespace by typing `C-c C-t C-n`:

CIDER displays a summary of the results in the minibuffer:

![test_result_all_namespace.jpg](images/test_result_all_namespace.jpg)

For details on test results, CIDER creates a buffer (\*cider-test-report\*) that provides details on the test execution including any errors:

![test_report_success.jpg](images/test_report_success.jpg)

CIDER provides a _Test-Report_ menu (with shortcut keys) to facilitate navigation and running of tests within (\*cider-test-report\*) buffer.

Now let's run a specific test. Switch to the `palindrome_test.clj` buffer, position point within the `(deftest string-palindrome-test-pos ...)` expression and type `C-c C-t C-t`. CIDER displays the results for the unit test in the minibuffer:

![test_result_single.jpg](images/test_result_single.jpg)

Now let's fabricate a unit test failure:

 * Within the `(deftest string-palindrome-test-pos ...)` expression change "racecar" to "racecars".
 * Type `C-x C-s` to save the changes.
 * Type `C-c C-k` to update the code in the REPL. 
 * Type `C-c C-t C-n` to re-run the unit tests

CIDER highlights the failed test and opens the \*cider-test-report\* to display details on the tests:

![test_report_failure.jpg](images/test_report_failure.jpg)

## More Information

In addition to running individual unit tests and all running all unit tests within a namespace, CIDER provides support for:

 * Running all unit tests in a project (`C-c C-t C-p`).
 * Running all unit tests loaded in the REPL (`C-c C-t C-l`).
 * Auto-running unit tests when a buffer is loaded/reloaded in the REPL (`C-c C-k`). This is accomplished by enabling the `cider-auto-test-mode` minor mode. This can be enabled on-demand by typing `M-x cider-auto-test-mode` or permanently by adding `(cider-auto-test-mode 1)` to your init.el.

The full set of test-related commands can be viewed from the _CIDER Interactions >> Test_ menu.


















