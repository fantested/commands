
## Session

|Command|Description|
|-------|-----------|
|tmux new -s \<session name\>|New|
|tmux ls|List|
|tmux a -t \<session name\>|Attach|
|ctrl-b d|Detach|
|ctrl-b (|Previous|
|ctrl-b )|Next|
|ctrl-b s|Choose|
|ctrl-b $|Rename|
|tmux kill-session -t \<session name\>|Kill|

## Window

|Command|Description|
|-------|-----------|
|ctrl-b c|New|
|ctrl-b p|Previous|
|ctrl-b n|Next|
|ctrl-b w|Choose|
|ctrl-b ,|Rename|
|ctrl-b &|Kill|

## Pane

|Command|Description|
|-------|-----------|
|ctrl-b “|Split vertically|
|ctrl-b %|Split horizontally|
|ctrl-b \<arrow key\>|Switch|
|ctrl-b x|Kill|
|ctrl-b [|Scroll up buffer|
