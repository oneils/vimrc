

```
h - move left
l - move right
j - move down
k - move up
```

## Insert Mode

```
a - move cursor at 1 symbol right for editing
A - move cursor  at the end of line for editing
o - move cursor at the new line for editing
O - create a new line above for additing
```

## Copy-Paste

```
yy or Y - copy line
dd - delete (cutting) the line

p - paste copied(deleted) text after current line
P - paste copied(deleted) text before current line
```
## Movements

```
gg - move cursor at the begging of the file
G  - move cursor at the ent of the file
w  - mote to the next word
b  - move to the word back (backword)
e  - move to the end of the next word
dd - delete current line
%  - move to the pair symbol (braces, etc)
20gg - will move cursor to specified line number 20
```

## Repeat command

Into command mode print `2w` to move to the next word twice

## Searching

```
f + symbol - find specified `symbol` at current line (; finds the next matching symbol)
F + symbol - fund specified `symbol` back
/ + any symbol or word to find it at the whole document from top to bottom
n - find next matching search result (used with /). This uses word Case.
N - navigate Up to the next found word
? + any symbol  to find `symbol` at the whole document from bottom to top.
t + symbol_to_be_find go to position before searching symbol, whe symbol_to_be_find is a symbol which were looking for
T + symbol - find the specified symbol and move cursor befor it backward
* - find thw word unser cursor (all found words in the file will be selected)
\ - ignore a symbol during the search
noh - turn the highlight off for the found word
dt + symbol - selete everything befor specified symbol
df + symbol - delete everything before the specified symbol
```

## Find into project's files

This can be achived either by `vimgrep` or `grep`

```
vimgrep def * - find any matches of def at all files
cnext - go to the next found matches
cprev - go to prev found matches
```

`grep` found all matches and display found results into terminal without vim integration.


## Navigation

```
`. - move cursor to the last edit position
` + symbol - go to saved bookmark, whene symbol - the name (signle charachter) for bookmark`
`D - go to the global bookmark`
gf - go the file under current cursor (e.g. new File(./my-file.txt) will go to the my-file.txt in case if such file exists into current path)
```

## Bookmarks

```
m + bookmar_name - create a bookmark with the name `bookmark_name` for current line.
mD - symbol - create a global bookmark with the name `symbol` (instead of D can be another char in UPPER case)
```

## Windows

With user-defined function:

function looks like

```
 function! WinMove(key)
     let t:curwin = winnr()
     exec "wincmd ".a:key
     if(t:curwin == winnr())
         if (match(a:key, '[jk]'))
           wincmd v
         else
           wincmd s
         endif
         exec "wincmd ".a:key
     endif
 endfunction
```

Using hotkeys

```
 Ctrl + k opens a new window above current or switch to window above
 Ctrl + h opens a new window at right or switch to the right window
 Ctrl + l opens a new window at left or switch to lelft window
 Ctrl + j opens a new window at bottom or switch to the bottom window
``` 

## Tmux

`tmux` will run a new tmux

```
Ctrl + B + % -  split screen vertically
Ctrl + B + " - split screen horizantally"
Ctrl + B + arrows - move between tmux screens
```

## Resize tmux windows

```
Ctrl + B:resize-pane -L 20 - decrease current window to 20 to left
```

`Ctrl + B:source-file ~/.tmux.conf` - reload tmux config file
`Ctrl + B + n` - create a new tmux window
`Ctrl + B + 1` - move to the 1st window
`Ctrl + B + $` - rename current tmux's session

`tmux attach -t session_name` - attach to specified session with name `session_name`




