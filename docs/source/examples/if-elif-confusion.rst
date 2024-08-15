If Elif Confusion
=================

Original Decompiled Code
-----------------------

.. image:: images/if-elif-confusion/IfElifConfusionOriginal.PNG

Relevant Bytecode Difference
----------------------------

.. image:: images/if-elif-confusion/IfElifConfusionBytecode.PNG

How to fix
----------

A good sign that that consecutive if statements are supposed to be elif statements are JUMP_FORWARD or JUMP_ABSOLUTE following the content of the if statements in the bytecode.

Patched Output
--------------

.. image:: images/if-elif-confusion/IfElifConfusionPatch.PNG
