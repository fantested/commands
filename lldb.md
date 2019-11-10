# Basic commands for lldb


## Commands
|command|description|
|-------|-----------|
|r \<args\>|run|
|s|step in|
|n|step over|
|finish|step out|
|b \<line num\|function name\>|set breakpoint|
|br l|list all breakpoints|
|br del 1|delete a breakpoint|
|fr v|show arguments and local variables for the current frame|
|p \<var\>|show the content of local variable "var"|
|ta v \<var\>|show the content of global variable "var"|
|expr \<expr\>|evaluate expression "expr"|
|thread list|list all the threads|
|t \<n\>|select thread n as the default thread|
|up|go to the previous frame|
|down|go to the next frame|
