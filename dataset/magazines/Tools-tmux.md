<h2 align="center">Tmux: A Terminal Multiplexer</h2>
**<p align="center">learning URLs: <a href="">jadi Tmux course</a></p>**

---

## What is Tmux?

Tmux (Terminal Multiplexer) is a powerful terminal application that allows users to open multiple terminal sessions within a single window or screen. It is particularly useful for managing multiple command-line tasks simultaneously, and it enables users to detach from a session and reattach later, even from a different device.

---

## What is Tmux used for?

Tmux is commonly used by developers, system administrators, and anyone who needs to run and manage multiple terminal sessions at once. It allows users to split a terminal window into multiple panes, switch between different sessions, and keep processes running in the background even if the terminal window is closed. This makes it ideal for running long processes, managing remote servers, and multitasking in a command-line environment.

---

## Where is Tmux used?

Tmux is widely used in environments where command-line multitasking is essential. This includes remote server management, software development, and scripting. It's especially popular in situations where users need to maintain persistent terminal sessions that can be accessed from different locations or devices.

Like Vim, Tmux has a steep learning curve, but once mastered, it becomes an invaluable tool for efficient terminal management. Users often customize Tmux with their own key bindings and configurations to suit their workflows.

---

<h2 align="center">Tmux commands</h2>
<p align="center">

| No. | Command                  | Description                                                                  |
| --- | ------------------------ | ---------------------------------------------------------------------------- |
| 1   | `ctrl + b`               | This is the prefix to enter Tmux command mode.                               |
| 2   | `ctrl + b %`             | This command splits the window horizontally.                                 |
| 3   | `ctrl + b "`             | This command splits the window vertically.                                   |
| 4   | `ctrl + b t`             | This command shows the time.                                                 |
| 5   | `ctrl + b arrows`        | These commands move between the different panes.                             |
| 6   | `ctrl + b z`             | This command zooms in on the current pane, and zooms out when pressed again. |
| 7   | `ctrl + b c`             | This command creates a new window.                                           |
| 8   | `ctrl + b (number)`      | This command switches to the window with the given number.                   |
| 9   | `ctrl + b d`             | This command detaches from the current Tmux session.                         |
| 10  | `tmux att -t (number)`   | This command attaches to the Tmux session with the given number.             |
| 11  | `ctrl + b ctrl + arrows` | This command changes the size of the current pane.                           |
| 12  | `ctrl + b :`             | This command allows you to enter Tmux commands, similar to Vim.              |
| 13  | `tmux new -s (name)`     | This command creates a new Tmux session with the given name.                 |
| 14  | `exit`                   | This command exits the current pane.                                         |
| 15  | `ctrl + b ?`             | This command shows all the available Tmux commands.                          |
| 16  | `ctrl + b s`             | This command shows all the Tmux windows.                                     |

</p>

---
