# Basic emacs commands
C-key: Ctrl+key  
M-key: Meta+key

## Help
|command|description|
|-------|-----------|
|C-h C-h|Help|

## File
|command|description|
|-------|-----------|
|C-x C-f|Find file|
|C-x C-s|Save file|
|C-x C-w|Write file as|

## Traverse
|command|description|
|-------|-----------|
|C-v, M-v|Move cursor forward/backward by a screen|
|C-n, C-p|Move cursor forward/backward by a line|
|M-f, M-b|Move cursor forward/backward by a word|
|C-f, C-b|Move cursor forward/backward by a character|
|C-a, C-e|Move cursor to beginning/end-of-line|
|M-a, M-e|Move cursor to beginning/end-of-sentence|
|M-<, M->|Move cursor to beginning/end-of-document|
|C-right, C-left|Move cursor forward/backward by a word|
|C-down, C-up|Move cursor forward/backward by a paragraph|

## Edit
|command|description|
|-------|-----------|
|C-d|Delete a character|
|M-d|Delete a word|
|C-k|Delete a line|
|M-k|Delete a sentence|
|C-@|Mark the beginning of a region|
|C-w|Cut|
|C-y|Paste|
|M-w|Copy|
|M-q|Wrap text|
|C-/, C-x u|Undo|

## Buffer
|command|description|
|-------|-----------|
|C-x C-b|List all buffers|
|C-x b|Switch to buffer|
|C-x s|Save buffer|
|C-x k|Kill buffer|
|C-x left|Left-cycle through buffers|
|C-x right|Right-cycle through buffers|

## Window
|command|description|
|-------|-----------|
|C-x 0|Close the active window|
|C-x 1|Close all windows except the active window|
|C-x 2|Split the active window into two windows horizontally|
|C-x 3|Split the active window into two windows vertically|
|C-x o|Switch active window to next window|
|C-x 4 C-f|Find file in other window|

## Search & Replace
|command|description|
|-------|-----------|
|C-s|Search forward|
|C-r|Search backward|
|M-%|Query replace|

## Universal Argument
|command|description|
|-------|-----------|
|C-u n C-n|Move cursor forward by n lines|
|C-u n C-f|Move cursor forward by n characters|

## Extended Command
|command|description|
|-------|-----------|
|m-x replace-string|Replace string|
|m-x recover-this-file|Recover a file|

## Exit
|C-g|Exit command mode|
|C-z|Exit emacs temporarily|
|C-x C-x|Save buffers and kill emacs|
