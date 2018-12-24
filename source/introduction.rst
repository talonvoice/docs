############
Introduction
############

Overview
========

Talon aims to bring programming, realtime video gaming, command line, and full desktop computer proficiency to people who have limited or no use of their hands, and vastly improve productivity and wow-factor of anyone who can use a computer.

`Join the Slack <https://join.slack.com/t/talonvoice/shared_invite/enQtMjUzODA5NzQwNjYzLTY1NzZjNzM4NjVhZjZhYWFlNmZkYmU2YzE2ZjQxZjcyMTgwNDk5NDg2YzhmZDRmNmEwYThkODEyYjY4ZGZmODE>`_ to talk, get hyped, or for help with the public beta.

Beta Info:

* Requires macOS El Capitan (10.11) or newer. Windows/Linux support is on the feature roadmap.
* Powerful voice control (depends on Dragon 6, or the free engine).
* Multiple algorithms for eye tracking mouse control (depends on a single Tobii 4C).
* Talon still functions if you only have an eye tracker, only have Dragon, or have neither. Only the respective features (eye tracking or voice recognition) will stop working without them.
* Noise recognition system (pop and hiss).
* Scriptable with Python 3.5 (via embedded pypy).

.. _getting-started:

Getting Started
===============

1. Install `Talon <https://talonvoice.com>`_.
2. Run the Talon app.
3. Add some scripts to ``~/.talon/user`` to voice commands and other behaviour (see the `Getting Scripts`_ section below).
4. If you have Dragon, start it up and then say "Go to sleep". If you don't have Dragon, you will be using the free engine which is enabled by default.
5. ``tail -f ~/.talon/talon.log`` for debug output
6. Further reading: `Dwighthouse's Unofficial Docs <https://github.com/dwighthouse/unofficial-talonvoice-docs>`_.

Using the Talon REPL
====================

While Talon is running, it provides a REPL. You can connect by running:

.. code-block:: bash

    ~/.talon/.venv/bin/repl

Getting Scripts
===============

There are a few options for getting Talon scripts. If you would like to get started quickly, take a look at `talon_community <https://github.com/dwiel/talon_community>`_.

If you would like official script examples to explore the different APIs for writing your own code, take a look at `Official Examples <https://github.com/talonvoice/examples>`_.

If you would like further examples, take a look at any of the below scripts. You can copy any scripts from these user-contributed repositories into ``~/.talon/user``:

* `dwighthouse <https://github.com/dwighthouse/talonvoice-scripts>`_
* `tabrat <https://github.com/tabrat/talon_user>`_
* `tuomassalo <https://github.com/tuomassalo/talon_user>`_
* `tuomassalo's Atom integration <https://github.com/tuomassalo/atom-talon>`_
* `dopey <https://github.com/dopey/talon_user>`_
* `pimentel <https://github.com/pimentel/talon_user>`_
* `JonathanNickerson <https://github.com/JonathanNickerson/talon_voice_user_scripts>`_
* `anonfunc <https://github.com/anonfunc/talon-user>`_
* `jcooper-korg <https://github.com/jcooper-korg/talon_user>`_
* `lexjacobs <https://github.com/lexjacobs/talon_user>`_
* `trishume <https://github.com/trishume/talon-config>`_
