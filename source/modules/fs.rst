talon.fs
==

.. module:: fs

.. function:: watch(path, cb)

   Watch `path` for changes and call ``cb(path: str, exists: bool)`` when they occur.

.. function:: unwatch(path, cb)

   Remove `cb` from the set of callbacks being watched for `path`.

.. code-block:: python

   from talon import fs

   def on_change(path, exists):
       if exists:
           print('changed', path)
       else:
           print('deleted', path)

   fs.watch('/path/to/stuff', on_change)
