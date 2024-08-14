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
- Missing or extra parentheses

- Decorator applied to a non-function (remove the decorator)

- Stray else blocks (remove the else and correct the indentation)

- Incomplete statements involving dictionaries and sets

Tips and How to Approach
^^^^^^^^^^^^^^^^^^^^^^^^
- Identify the line where the error occurs by clicking the dropdown and checking if anything fails to follow Python syntax rules. The error might be 1 or 2 lines above or below the flagged line.

- Close any unclosed parentheses, brackets, etc.

- Delete any code that does not resemble valid Python syntax. For example, a fragment like <mask34 at the end of a line.

- If the fix is not immediately clear, comment out the flagged line and return to it later after examining the bytecode diff.


Step 2
------

Semantic errors are caused because the bytecode produced when compiling the code outputted by the model does not match the bytecode in the `.pyc` file provided.

Common Semantic Issues  
~~~~~~~~~~~~~~~~~~~~~~

- Large dictionaries  
- Large number of arguments  
- Super long statements  
- Nested control flow  

General Tips and How to Approach  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- Follow the code object that fails the equivalence report by clicking the dropdown that flags semantic errors.  
- Lines of code may sometimes be out of order, leading to control flow errors.

Different and Missing Bytecode  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Different Bytecode
^^^^^^^^^^^^^^^^^^

- Ignore the following differences:

  - Index differences (will fix itself as you address other bytecode and control flow issues)

  - Empty line differences

- Cases to fix:

  - Dictionaries: If the model cannot generate long dictionaries, manually extend the dictionary using the correct bytecode as a reference.

  - Bytecode order mismatch: The bytecode instructions for a line of code may be in the wrong order, creating incorrect statements.

  - Completely different bytecode: This usually indicates a control flow issue, and the two should be fixed together.

Missing Bytecode
^^^^^^^^^^^^^^^^

- Investigate the surrounding lines of flagged bytecode to identify if identical bytecode is misplaced.
- Some lines may need to be recreated manually when bytecode is missing.

Control Flow Errors
~~~~~~~~~~~~~~~~~~~


Control flow errors occur when jump targets from control structures like `if-else` statements, loops, `try-except` blocks, function returns, or misplaced lines do not match between the model-generated and original bytecode.

Disclaimers  
^^^^^^^^^^^  
- Different control flow structures may exist across Python versions.  
- Jump targets are bytecode offsets, shown as numbers in parentheses indicating the destination. Occasionally, you'll encounter a large jump target number that seems out of range.

General Tips and How to Approach  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^  
- A small delta (1 to 10) in jump target differences is usually acceptable and often stems from missing bytecode or incorrect lines.  
- Be aware of the following control flow interpretation issues:  
  - `if` statements might be incorrectly interpreted as `while` loops, especially if there's a `break` or `continue` inside the `if` block.  
  - Nested `if` statements and `else` blocks may need to be merged.  
  - Consecutive `if` statements might need to be converted into `elif` statements.  
  - The model might struggle with `pass`, `continue`, or `break` statements.

Main Objective  
^^^^^^^^^^^^^^  
- Match the jump targets between the bytecode and the original code.  
- Look for significant deltas between jump targets, and use constants near the control flow statements to find the source code line causing the issue.  
- Ensure the entry and exit points of control flow blocks align. Common markers like `jump absolute` or `jump backwards` often indicate loop boundaries, while mistranslations of `break`, `continue`, or `return` statements can disrupt control flow.









