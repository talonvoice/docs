clip
====

.. module:: talon.clip

Functions for interacting with the clipboard.

.. function:: get
    
    Get the contents of the clipboard.

    :rtype: str

.. function:: set(s)

    Set the contents of the clipboard.

    :param str s: the new clipboard content.

.. function:: serial

    Some kind of clipboard epoch number?

.. function:: await_change(timeout=0.5, after=None)

    Wait for the clipboard contents to change and return the new contents.

    :param float timeout: if the clipboard hasn't changed after this 
        long, return the current contents.
    :param after: 
    :rtype: :obj:`str` or :obj:`None`
