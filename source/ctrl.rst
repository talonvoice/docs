ctrl
====

.. module:: ctrl

.. function:: key_press(key, *, cmd=False, shift=False, ctrl=False, alt=False, fn=False, down=None, up=None, hold=0, wait=0)

  Simulate a key press. `key` and the various modifier arguments determine which key is pressed.

  `down` and `up` determine whether this should be a key down or key up event. If neither is passed,
  press and release immediately (i.e., do both).

  :param key: The key to press.
  :param bool cmd, shift, ctrl, alt, fn: Modifier keys to apply
  :param down: emit a key down event
  :type down: :obj:`bool` or :obj:`None`
  :param up: emit a key up event
  :type up: :obj:`bool` or :obj:`None`
  :param int hold: How long should the key be held for?
  :param int wait: something???

.. function:: mouse(x, y, dx=0, dy=0)

  Move the mouse.

  :param int x:
  :param int y:
  :param int dx:
  :param int dy:

.. function:: mouse_pos

  Get the cursor's current position.

.. function:: mouse_click(x=None, y=None, button=0, times=1, *, down=None, up=None, hold=0, wait=0)

  Click the mouse. If `x` and `y` are not :obj:`None`, click at coordinates (`x`, `y`). Otherwise,
  click at the current mouse position.

  :param x:
  :type x: :obj:`int` or :obj:`None`
  :param y:
  :type y: :obj:`int` or :obj:`None`
  :param int button: selects left/right/middle click and is probably 0, 1, or 2?
  :param int times:
  :param down:
  :type down: :obj:`bool` or :obj:`None`
  :param up:
  :type up: :obj:`bool` or :obj:`None`
  :param int hold: How long should the mouse button be held for?
  :param int wait: something???

.. function:: mouse_buttons_down

  Returns which mouse buttons are currently pressed.

.. function:: mouse_scroll(x=0, y=0, by_lines=False)

  :param int x: vertical distance (positive values move down)
  :param int y: horizontal distance (positive values move right)
  :param bool by_lines: probably a a placebo.

