talon.audio
===========

.. module:: audio

.. function:: noise.register(topic, cb: function)

   Register a noise callback. Valid topics:

       - ``""`` - an empty string registers the callback for all noises.
       - ``"hiss_start"``
       - ``"hiss_end"``
       - ``"pop"``

.. function:: noise.unregister(topic: str, cb: function)

   Unregister a noise callback.

.. code-block:: python 

   from talon import audio

   def on_noise(noise):
       print(noise)
   audio.noise.register('', on_noise)
