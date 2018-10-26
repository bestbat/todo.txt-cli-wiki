Here's how to install and run the Todo.txt CLI:

0. (_Windows only_) [Download and install Cygwin](http://cygwin.com/install.html). Cygwin provides a Unix-environment for Windows; Todo.txt needs just the Bash shell and some common Unix tools, so a minimal installation will do just fine (Another suggestion is to use git on windows - it's smaller and have sh builtin [git on windows](http://git-scm.com/)).

1. [Download the latest stable release of Todo.txt CLI](http://github.com/todotxt/todo.txt-cli/releases) (available as a ZIP or TAR archive) and extract it.
Mac users: There is a [Homebrew](https://brew.sh) package for todo.txt - install using `brew install todo-txt`.

2. Open a command window. On Windows, this is _Cygwin Bash Shell_ (_not_ Command Prompt!); elsewhere, this is often called _Terminal_. It usually presents you with a `$` prompt. `cd` into the directory where you extracted todo.sh. Make the todo.sh script executable:

```bash
$ chmod +x todo.sh
```

3. Type `./todo.sh` to see the usage message. You're ready to go!  To start adding tasks, type `./todo.sh add "My new task"`

## Optional

4.  Install the Bash completion, either system-wide, for all users:

```bash
$ sudo cp todo_completion /etc/bash_completion.d/todo
```

_or_ put it somewhere in your home directory and source it from your `.bashrc`:

```bash
$ source todo_completion
```

Now you can type `$ ./todo.sh ad<Tab>` and Bash will autocomplete the action to `$ ./todo.sh add`. Any words that begin with + or ` will be completed using projects or contexts, respectively. Task numbers will append the task text as a shell comment.

Note: If you define an alias (e.g. `t`) to todo.sh, you need to explicitly enable completion for it, too (also put this into your `.bashrc`):

```bash
$ complete -F _todo t
```

5. Want more? See the full list of configuration tweaks, enhancements and recommendations on the [[Tips and Tricks]] page.

6. Something missing? Todo.txt is extensible; many users have already written Add-ons listed on the [[Todo.sh Add on Directory]] page.

7. Having problems? Have a look at the [[Troubleshooting]] page, or ask on the friendly [mailing list](http://groups.yahoo.com/group/todotxt/).