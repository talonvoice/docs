fs
==

.. module:: talon.fs

.. function:: watch(path, cb)

  Watch `path` for changes and call ``cb(path, exists)`` when they occur.

  :param str path: the path to watch.
  :param cb: a function taking two arguments: `path` (:obj:`str`), and `exists` (:obj:`bool`).

.. function:: unwatch(path, cb)

  Remove `cb` from the set of callbacks being watched for `path`.

  :param str path: the path to watch.
  :param cb: A previously registered callback function.
