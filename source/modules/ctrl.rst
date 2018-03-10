talon.ctrl
==========

.. module:: ctrl

.. function:: key_press(key, ...)

   Simulate a key press. To press and hold, pass ``down=True``. To release, pass ``up=True``

   :param str key: The key to press. Can be any symbol your keyboard can type, as well as any special key from :ref:`Key Names <ctrl_key_names>`.
   :param bool cmd, shift, ctrl, alt, fn: modifier keys to apply
   :param bool down, up: hold or release the key
   :param int hold: duration in microseconds to hold the key down
   :param int wait: duration in microseconds to wait between key presses

.. function:: mouse(x, y, dx=0, dy=0)

   Move the mouse.

   :param int x, y: absolute mouse position
   :param int dx, dy: relative mouse movement

.. function:: mouse_pos -> (x, y)

   Get the cursor's current position.

.. function:: mouse_click(x=None, y=None, button=0, times=1, ...)

   Click the mouse. If `x` and `y` are not :obj:`None`, click at coordinates (`x`, `y`). Otherwise, click at the current mouse position.

   :param int x, y: absolute mouse position, can be omitted to click in the current position
   :param int button: ``0`` is left click, ``1`` is right, ``2`` is middle, ``3+`` are additional mouse buttons
   :param int times:
   :param bool down, up: hold or release the button
   :param int hold: duration in microseconds to hold the mouse button
   :param int wait: duration in microseconds to wait between clicks

.. function:: mouse_buttons_down -> list

   Returns which mouse buttons are currently pressed as a list of numbers starting with ``0``.

.. function:: mouse_scroll(x=0, y=0)

   :param int x: vertical distance (positive values move down)
   :param int y: horizontal distance (positive values move right)

.. code-block:: python 

   from talon import ctrl

   ctrl.key_press()

.. _ctrl_key_names:

.. csv-table:: Key Names
   :header: "Name", "Alternate"

   "alt"
   "backspace","bksp"
   "capslock"
   "cmd"
   "ctrl"
   "delete","del"
   "down"
   "end"
   "escape","esc"
   "f1"
   "f2"
   "f3"
   "f4"
   "f5"
   "f6"
   "f7"
   "f8"
   "f9"
   "f10"
   "f11"
   "f12"
   "f13"
   "f14"
   "f15"
   "f16"
   "f17"
   "f18"
   "f19"
   "f20"
   "fn"
   "help"
   "home"
   "left"
   "mute"
   "pageup","pgup"
   "pagedown","pgdown"
   "return"
   "enter"
   "right"
   "ralt"
   "rctrl"
   "rshift"
   "shift"
   "space"
   "tab"
   "up"
   "voldown"
   "volup"
   "keypad_clear"
   "keypad_enter"
   "keypad_decimal"
   "keypad_plus"
   "keypad_divide"
   "keypad_minus"
   "keypad_equals"
   "keypad_0"
   "keypad_1"
   "keypad_2"
   "keypad_3"
   "keypad_4"
   "keypad_5"
   "keypad_6"
   "keypad_7"
   "keypad_8"
   "keypad_9"
