############
Introduction
############

.. _getting-started:

Getting Started
===============

1. Install `Talon <talonvoice.com>`_.
2. Run the Talon app.
3. Copy ``std.py`` from `<https://github.com/talonvoice/examples>`_ 
   into ``~/.talon/user/`` - read the files for some example commands.
4. Run Dragon.app
5. ``tail -f ~/.talon/talon.log`` for debug output

Using the Talon REPL
====================

While Talon is running, it provides a REPL via UNIX socket. You can connect to it with::

    nc -U ~/.talon/.sys/repl.sock

If you miss readline support, you can install `rlwrap <https://github.com/hanslub42/rlwrap>`_
(available in homebrew) and run::

    rlwrap nc -U ~/.talon/.sys/repl.sock
