.. |br| raw:: html

    <br>

############
Introduction
############

Overview
========

Talon aims to bring programming, realtime video gaming, command line, and full desktop computer proficiency to people who have limited or no use of their hands, and vastly improve productivity and wow-factor of anyone who can use a computer.

`Join the Slack <https://join.slack.com/t/talonvoice/shared_invite/enQtMjUzODA5NzQwNjYzLTY1NzZjNzM4NjVhZjZhYWFlNmZkYmU2YzE2ZjQxZjcyMTgwNDk5NDg2YzhmZDRmNmEwYThkODEyYjY4ZGZmODE>`_ to talk, get hyped, or for help with the public beta.

Beta Info:

* Requires macOS El Capitan (10.11) or newer. Windows/Linux support is on the feature roadmap.
* Powerful voice control (can use Dragon 6, or a free speech recognition engine that comes with Talon).
* Multiple algorithms for eye tracking mouse control (depends on a single Tobii 4C).
* Noise recognition system (pop and hiss).
* Scriptable with Python 3.5 (via embedded pypy).
* Talon will run fine without an eye tracker, or if you don't have a speech recognition engine set up. Only the respective features will fail to work in that case.

.. _getting-started:

Getting Started
===============

1. Install `Talon <https://talonvoice.com>`_.
2. Run the Talon app.
3. Add some scripts to ``~/.talon/user`` to add voice commands and other behaviour to Talon (see the `Getting Scripts`_ section below).
4. If you have Dragon, start it up and then say "Go to sleep". If you don't have Dragon, there is a builtin free engine that is enabled by default when you install a language from the Speech Recognition menu.
5. Run ``tail -f ~/.talon/talon.log`` in a terminal for debug output.
6. If using Talon Community:
  * To list commands, say `"help context" <https://whalequench.club/blog/2019/09/03/learning-to-speak-code.html#all-contexts>`_ or `"help <context name>" <https://whalequench.club/blog/2019/09/03/learning-to-speak-code.html#commands-for-a-context>`_, |br| e.g., `"help alphabet" <https://whalequench.club/blog/2019/09/03/learning-to-speak-code.html#alphabet>`_.
  * See Emily Shea's: `Getting Started with Voice Driven Development <https://whalequench.club/blog/2019/09/03/learning-to-speak-code.html>`_.

Using the Talon REPL
====================

While Talon is running, it provides a REPL. You can connect by running:

.. code-block:: bash

    ~/.talon/.venv/bin/repl

Getting Scripts
===============

If you would like to get started quickly, you can clone the entire community repository into your ``~/.talon/user`` directory: `talon_community <https://github.com/dwiel/talon_community>`_.

If you would like minimal official examples to explore the different APIs for writing your own code, take a look at `Official Examples <https://github.com/talonvoice/examples>`_.
