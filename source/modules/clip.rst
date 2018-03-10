talon.clip
====

.. module:: clip

System clipboard interface.

.. function:: get() -> str

   Get the contents of the clipboard.

.. function:: set(contents: str)

   Set the contents of the clipboard.

.. function:: serial() -> int

   The clipboard serial increments on each clipboard update and can be used to see if the clipboard has changed.

.. function:: await_change(timeout=0.5, serial=None) -> str

   Wait for the clipboard contents to change and return the new contents.

   :param float timeout: if the clipboard hasn't changed after this many seconds, returns ``None``
   :param int serial: if not provided, defaults to ``serial()``
   :rtype: :obj:`str` or :obj:`None`

.. code-block:: python 

   from talon import clip

   s = clip.get()
   print(s)
   s = clip.await_change()
   print(s)
   clip.set(s.upper() + ' clipboard test')
