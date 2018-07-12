talon.applescript
=================

.. module:: applescript

.. function:: check(source: str)

   Check AppleScript `source` for syntax errors. Raises `applescript.ApplescriptErr`.

.. function:: run(source: str) -> str

   Run AppleScript `source`. Raises `applescript.ApplescriptErr` on error. Returns a raw AppleScript encoding of the script's result.

.. code-block:: python

   from talon import applescript

   applescript.run(r'''
   tell application "System Events"
       display notification "Hello world."
   end tell
   ''')
