dispatch
========

.. module:: dispatch

.. class:: Dispatch

  Does event dispatching things. Mostly builtin subclasses.

  .. method:: register(self, topic, cb)

    Register a callback function `cb` for `topic`.

    :param str topic: The topic.
    :param cb: A function; signature varies by subclass.
