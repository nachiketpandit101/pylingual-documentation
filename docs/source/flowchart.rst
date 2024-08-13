Flowchart
====

Patching Algorithm:
-------------------
for code object in errors:
   if code object is compilation/syntax:
      check for decorators above non-function statements

      check for incomplete dictionary

      check for mismatched parentheses or quotations

      check for wrong indentation

   elif code object is different bytecode:
      check for long dictionary

      check for incorrect boolean expression

      function call order mismatch

      incorrect statement

   elif code object is control flow:
      case loop:
         if/while confusion

         break/pass/continue confusion

         hallucinated while post-test (3.10)

      case if statement:
         if segmentation error

         incorrect else block

      case exception:
         finally
      case default:
         return statement
   else:
      contact support team
