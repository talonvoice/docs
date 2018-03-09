audio
=====

.. module:: talon.audio

.. object:: record

  Singleton instance of :class:`Record`

.. object:: noise

  Singleton instance of :class:`Noise`

.. class:: Record
  
  Subclass of :class:`dispatch.Dispatch`.

  Only one valid topic: ``'record'``.

  Records audio?

  `count`, `samples`

.. class:: Noise
  
  Subclass of :class:`dispatch.Dispatch`.

  .. method:: register(topic, cb)

    Its callbacks receive one argument, the topic.

    :param str topic: One of: ``'hiss_start'``, ``'hiss_end'``, ``'pop'``.
    :param cb: A function that takes a :obj:`str`.
