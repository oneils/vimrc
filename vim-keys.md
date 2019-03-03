 # Vim tricks

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
```

## Repeat command

Into command mode print `2w` to move to the next word twice

## Searching

```
f + symbol - find specified `symbol` at current line (; finds the next matching symbol)
/ + any symbol or word to find it at the whole document from top to bottom
n - find next matching search result (used with /). This uses word Case.
? + any symbol  to find `symbol` at the whole document from bottom to top.
```

m + bookmar_name - create a bookmark with the name `bookmark_name` for current line.


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
