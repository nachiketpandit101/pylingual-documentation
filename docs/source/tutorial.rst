Tutorial
========

Step 1
------

The first goal of the process is to address compilation, syntax, and indentation errors before tackling semantic errors. Here are common causes of these errors and how to fix them. 
It’s possible that there are only semantic errors from the start, in which case you can skip to step 2.


Compilation and Syntax Errors
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Common Compilation and Syntax errors
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-Missing or extra parentheses

-Decorator applied to a non-function (remove the decorator)

-Stray else blocks (remove the else and correct the indentation)

-Incomplete statements involving dictionaries and sets

Tips and How to Approach
^^^^^^^^^^^^^^^^^^^^^^^^
-Identify the line where the error occurs by clicking the dropdown and checking if anything fails to follow Python syntax rules. The error might be 1 or 2 lines above or below the flagged line.

-Close any unclosed parentheses, brackets, etc.

-Delete any code that does not resemble valid Python syntax. For example, a fragment like <mask34 at the end of a line.

-If the fix is not immediately clear, comment out the flagged line and return to it later after examining the bytecode diff.


Step 2
------


