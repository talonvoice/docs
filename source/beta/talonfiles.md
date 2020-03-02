# Talon File

Talon can be configured via talonfiles (`.talon` extension). These are similar in syntax to yaml, the most notable difference
being you can have multiple of the same key.

A talon file can:

* implement actions
* define overall context for commands and actions
* define voice commands

See [here](#definition-examples) for a complete example.

## Format

There are 2 sections to a talon file

1. Context - the first section, above the dash/hyphen. Specifies where the actions and/or commands will be active. [Examples here](#context-examples)
2. Definitions - the second section, below the dash. Specifies the voice commands and/or actions. [Details here](#definitions), with full [examples here](#full-examples)

```yaml
# your context goes here
-
# your definitions go here
```

### Context

The context can take 3 different keys, `os`, `app`, `title` by default or [custom keys](#custom-context) that you define.

#### OS

OS can have one of three values:

* Windows
* Linux
* Mac

#### App

App can take a plain text value of the application name you want to filter by

#### Title

Title can take a plain text value or a regular expression to filter by.

#### Context Examples

```yaml
os: windows
os: linux
app: Slack
app: slack.exe
app: Teams
-
```

The above restricts the commands:

    - linux or windows OS; and 
    
    - an app name of Slack, slack.exe, or Teams.
    
Any commands would not be available on Mac OS as it does not match the OS filter.

You can also filter by window title.

```yaml
app: Gnome-terminal
title: /emacs/
-
```

In this case the definitions would only be active for the Gnome-terminal app with a window title that contains emacs
The /'s around emacs mean it's a regular expression, so you can do all kinds of matching. This should be done sparingly in scripts you intend to share.

#### Precedence

The more keys you have in the context, the more specific it will be. For example:

```yaml
app: Slack
os: Linux
title: /Talon/
```

is more specific than:


```yaml
app: Slack
title: /Talon/
```

which is more specific than:

```yaml
app: Slack
```

#### Custom Context

You can define your own context for talon files, using Python. This allows you to get creative about where your commands
are active. For instance, if you want to activate a specific programming language's commands in any editor using
os/app/title alone may not suffice, or it may require a rather long context. Instead you can create a Python file
to specify a context and reference that in your talon file.

```python
from talon import Context
from helpers import is_go_lang

ctx = Context()

@ctx.action_class('code')
class CodeActions:
    def language(): 
        if is_go_lang():
            return "golang"
        else:
            return ""       
```

Your talon file takes the string value given to `@ctx.action_class` and the method name to create a context filter:

```yaml
code.language: golang
-
```

Now the commands in golang.yml will only be active if the language function returns "golang" (it's up to you how it decides
if it should return that). 

### Definitions

The definition section contains your action implementation, or voice command definitions.

#### Voice Command

Most talon files will be full of voice commands. What you want to say is the key, and what to do is the value.

#### Voice keys

You can make some words optional when speaking, to make commands flow more naturally.

`()` - means a group of words

`[]` - means optional

`|` - means or

So for this command:

`([channel] unread next | goneck): key(alt-shift-down)`

You can say:

```
- "channel unread next"  

- "unread next"

- "goneck" 

- "unread next"

```

`Channel` is optional, `unread next` must be said together or you can say `goneck`

#### Inserting static text

```yaml
at sign: insert("@")
```

The above means when you say "at sign" Talon will type @ wherever you currently have focus.

#### Pressing keys sequentially

```yaml
slap: key(home enter)
```

The above will press the key home, then enter.

#### Pressing keys concurrently

```yaml
open tab: key(ctrl-t)
```

The above will press the control home and the t key at the same time.

#### Multiple instructions

If you want to press a key then type some text you can put those instructions on new lines:

```yaml
git commit:
    insert("git commit")
    key(enter)
```

This will type `git commit` then press enter

#### Action Implementation

If an action already exists (there are quite a few default ones) and you would like to implement it for a specific context
you use the `action` function as the key with the instructions for talon as the value.

```yaml
action(edit.line_down):
	key(down home)
	
action(edit.line_end):
	key(end)
```

The above implements the `edit.line_down` and `edit.line_end` action. This allows you to have different instructions executed for
different context for the same spoken command.

The same applies for custom made actions, but you will need the path to the file containing the action separated by dots,
plus the name of the method. If you had a file called `myactions.py` inside `user/code/` with an action class that has
a function `empty_action` you would need `user.code.myactions.empty_action` as the action name in your talon file.

```yaml
action(user.code.myactions.empty_action):
    insert("hey I made an action")
```

#### Calling actions

If you want to call an action when a command is spoken, you use the same path style as described above. If you had a file
 called `myactions.py` inside `user/code/` with an action class that has a function `my_action`
  you would need `user.code.myactions.my_action` as the action name in your talon file.

```yaml
do my action: user.code.myactions.my_action()
```

Now when you say "do my action" the code inside my_action will be called. This is good for when you want to do more
than just key presses e.g. switch which app has focus.

## Full Examples

The config files below demonstrate how you could control a terminal using built-in actions, a custom action
 and some voice commands.

terminal.talon:
```yaml
os: linux
app: /.*terminal/
-
action(app.tab_open):
  key(ctrl-shift-t)
action(app.tab_close):
  key(ctrl-shift-w)
action(app.tab_next):
  key(ctrl-pagedown)
action(app.tab_previous):
  key(ctrl-pageup)
go tab <number>:
  user.code.keys.modifier_key("alt", number)
run last:
  key(up)
  key(enter)
kill all:
  key(ctrl-c)
action(edit.paste):
  key(ctrl-shift-v)
action(edit.copy):
  key(ctrl-shift-c)
```

tabs.talon:
```yaml
open tab: app.tab_open()
last tab: app.tab_previous()
next tab: app.tab_next()
close tab: app.tab_close()
reopen tab: app.tab_reopen()
```

standard.talon:
```yaml
copy: edit.copy()
paste: edit.paste()
```

code/keys.py
```python
from talon import Module, Context, actions, ui

mod = Module()

@mod.action_class
class Actions:
    def modifier_key(modifier: str, key: str):
        """Presses the modifier plus supplied number"""
        res = "-".join([modifier] + [str(key)])
        actions.key(res)
```

This shows how the "copy" command is mapped to the action edit.copy() which inside a terminal would be control, shift and c pressed together.
This means other apps can implement it differently (e.g. most apps do control and c for copying).
Multiple instructions are demonstrated with "run last" which is 2 instructions for talon: press up then press enter.
Finally custom user actions are demonstrated with "go tab" and the `modifier_key` action
