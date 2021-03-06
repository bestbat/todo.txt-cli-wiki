Todo.sh add-ons let you add new todo.sh actions or change (override) default actions.  Visit the [[Todo.sh Add-on Directory]] to find browse available add-ons.

## Installing Add-ons

Add-ons can be installed into the `$HOME/.todo.actions.d` directory or any other directory configured via `$TODO_ACTIONS_DIR`.

Create this directory with the following bash shell commands:

```bash
$ mkdir -p ~/.todo.actions.d
```

You must name add-ons after the action you want to add or override. For example, create a new "review" action by installing an add-on to `.todo.actions.d/review`.

After installing the add-on, you must make it executable.

For example:

```bash
$ chmod +x ~/.todo.actions.d/review
```

Use the new or overridden action the normal todo.sh way.

For example:

```bash
$ todo.sh review
```

You can force todo.sh to use a default action instead of an overridden action by prefixing the action's name with the word, "command".

For example:

```bash
$ todo.sh command ls
```

## Creating Add-ons

Add-ons may be written in any programming language your operating system supports. The first command-line argument to the add-on will be the action called or the word "usage"; the remaining arguments, if any, will be those provided by the user. For example:

```bash
$ todo.sh _dummy_action foo bar
First argument: _dummy_action
Remaining arguments:
	* foo
	* bar
```

If the first argument is _usage_, you should provide a short usage message that will be displayed when the user calls `todo.sh -h`.

Todo.sh will also provide your script with several environmental variables including the following documented in todo.sh's usage message:

* `TODOTXT_PRESERVE_LINE_NUMBERS`
* `TODOTXT_VERBOSE`
* `TODOTXT_PLAIN`
* `TODOTXT_AUTO_ARCHIVE`
* `TODOTXT_FORCE`
* `TODOTXT_DATE_ON_ADD`

and the following environmental variables not documented in the usage message:

* `TODO_SH` - name of the todo.sh script, use in the usage message
* `TODO_FULL_SH` - complete path to calling todo.sh script, use for invoking todo.sh
* `TODOTXT_CFG_FILE` - complete path to user's todo.sh configuration file
* `TODO_DIR` - complete path to the todo.txt file

## [[Creating Add-ons: Examples]]

## Aliasing Add-ons

You may want to allow short aliases for those new commands (e.g. "pv" as alias for "projectview")

There is a small issue if you simply duplicate or symlink the add-on file: the corresponding help snippet will be duplicated as well in the output of the todo.sh help command. To avoid that, you can create aliases by creating short add-ons such as this example (replace `projectview` by the command you want to call with your alias):

```bash
#!/bin/bash
[ "$1" = "usage" ] && exit 0
shift
"$TODO_FULL_SH" projectview "$@"
```
