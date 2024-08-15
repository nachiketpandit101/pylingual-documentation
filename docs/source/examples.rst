Examples
========

Here are some common examples of the Pylingual patching process that may help with patching a file.
Heads up, in the Relevant Bytecode Difference, the left side is the uploaded pyc bytecode, and the
right side is the bytecode producded by the original decompiled code.

Compilation and Syntax Errors
-----------------------------
.. toctree::
   :maxdepth: 1

   examples/decorators
   examples/incomplete-dictionary
   examples/parentheses
   examples/indentation

Semantic Errors (Different Bytecode)
-----------------------------------
.. toctree::
   :maxdepth: 1

   examples/longDictionary
   examples/incorrect-boolean
   examples/function-call-mismatch
   examples/incorrect-statement

Semantic Errors (Different Control Flow)
---------------------------------------
.. toctree::
   :maxdepth: 1

   examples/if-while-confusion
   examples/break-pass-continue-confusion
   examples/hallucinated-while
   examples/if-segmentation
   examples/incorrect-else
   examples/try-except
   examples/return


