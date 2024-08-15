If While Confusion
==================

Original Decompiled Code
-----------------------

.. image:: images/if-while-confusion/IfWhileOriginal.PNG

Relevant Bytecode Difference
----------------------------

.. image:: images/if-while-confusion/IfWhileBytecode.PNG

How to fix
----------

There isn't really a straightforward way to identify this issue without understanding the difference between jump targets of Decompiled and Original Bytecode, and considering subtle hints such as unusual break statements.

Due to above mentioned fact and how common this issue pops up, I suggest that when you encounter a control flow issue involving a if or while loop, simply try changing the while into if and vice versa to see if this resolves the issue.

Patched Output
--------------

.. image:: images/if-while-confusion/IfWhilePatch.PNG