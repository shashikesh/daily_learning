# Vim Shortcuts and Commands

## Basic Modes
```plaintext
i           Insert before the cursor
a           Insert after the cursor
Esc         Return to Normal mode
:           Enter Command-Line mode (e.g., :w, :q)
```

## File Management
```plaintext
:w          Save the file
:q          Quit
:wq         Save and quit
:x          Save and quit (only if changes exist)
:q!         Quit without saving
:e <file>   Open a file
:n          Go to the next file
:prev       Go to the previous file
```

## Cursor Movement
```plaintext
h           Move left
l           Move right
j           Move down
k           Move up
0           Jump to the beginning of the line
^           Jump to the first non-whitespace character
$           Jump to the end of the line
w           Jump to the start of the next word
e           Jump to the end of the current/next word
b           Jump to the beginning of the previous word
gg          Go to the beginning of the file
G           Go to the end of the file
:n          Go to line number n (e.g., :42 for line 42)
```

## Editing Text
```plaintext
x           Delete the character under the cursor
dw          Delete a word
dd          Delete the current line
d$          Delete to the end of the line
u           Undo
Ctrl+r      Redo
yy          Copy (yank) the current line
yw          Yank a word
p           Paste after the cursor
P           Paste before the cursor
```

## Visual Mode
```plaintext
v           Start character-based selection
V           Start line-based selection
Ctrl+v      Start block (column) selection
y           Yank the selected text
d           Delete the selected text
>           Indent the selected block
<           Un-indent the selected block
```

## Search and Replace
```plaintext
/text       Search for text
?text       Search backward for text
n           Jump to the next search match
N           Jump to the previous search match
:%s/old/new/g       Replace all occurrences of old with new
:%s/old/new/gc      Replace all with confirmation
```

## Window Management
```plaintext
:split      Split horizontally
:sp         Shortcut for split
:vsplit     Split vertically
:vsp        Shortcut for vsplit
Ctrl+w w    Switch between windows
Ctrl+w q    Close a window
Ctrl+w h    Move to the left window
Ctrl+w l    Move to the right window
Ctrl+w k    Move to the window above
Ctrl+w j    Move to the window below
```

## Macros
```plaintext
qa          Start recording a macro into register a
<commands>  Perform desired actions
q           Stop recording
@a          Play the macro stored in register a
```

## Registers and Buffers
```plaintext
"0p         Paste from the yank register
:ls         List all buffers
:b<n>       Switch to buffer n
```

## Indentation
```plaintext
>>          Indent the current line
<<          Un-indent the current line
=%          Re-indent the current block
```

## Help
```plaintext
:help       Open help
:help <cmd> Get help for a specific command (e.g., :help dd)
