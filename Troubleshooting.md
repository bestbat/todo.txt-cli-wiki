*I get "Fatal Error: Cannot read configuration file /Users/myusername/.todo/config" when launching todo.sh*

Create the <code>~/.todo/config</code> file manually.  Here's some example content:
<pre><code>export TODO_DIR="$HOME/Dropbox/todo"
export TODO_FILE="$TODO_DIR/todo.txt"
export DONE_FILE="$TODO_DIR/done.txt"
export REPORT_FILE="$TODO_DIR/report.txt"
export TMP_FILE="/tmp/todo.tmp"
export TODOTXT_DEFAULT_ACTION=ls</code></pre>