talon.app
===========

.. module:: app

.. function:: notify(title: str, subtitle: str, body: str, sound: bool)

   Display a desktop notification, optionally playing a sound.

.. code-block:: python 

   from talon import app

   app.notify(body='Hello world')
   app.notify('Hello world',
              'Welcome to Talon',
              'Enjoy your stay.', sound=True)

