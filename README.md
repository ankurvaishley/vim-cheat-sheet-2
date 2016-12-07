# vim-cheat-sheet

## Move horizontally

    0   Move to beginning of line

    _   Move to first non-blank character of the line

    g_  Move to last non-blank character of the line

    fX  To next 'X' after cursor, in the same line (X is any character)

    FX  To previous 'X' before cursor (f and F put the cursor on X)

    tX  Til next 'X' (similar to above, but cursor is before X)

    TX  Til previous 'X'

    ;   Repeat above, in same direction

    ,   Repeat above, in reverse direction

    %   Jump to matching bracket { } [ ] ( )

## Move vertically

    gg  Move to first line

    G   Move to last line

    nG  Move to n'th line of file (n is a number; 12G moves to line 12)


    H   Move to top of screen

    M   Move to middle of screen

    L   Move to bottom of screen


    z.  Scroll the line with the cursor to the center of the screen

    zt  Scroll the line with the cursor to the top

    zb  Scroll the line with the cursor to the bottom


    Ctrl-D  Move half-page down

    Ctrl-U  Move half-page up

    Ctrl-B  Page up

    Ctrl-F  Page down

    Ctrl-O  Jump to last (older) cursor position

    Ctrl-I  Jump to next cursor position (after Ctrl-O)

    Ctrl-Y  Move view pane up

    Ctrl-E  Move view pane down

## Avoiding escape key 

    Ctrl-c  Escape equivalent

## Visual block

    shiftj shiftJ     Join multiple lines in one line

    Column + c<char>  Change character in column

    YVR<char>         Replace all the line with a repeated char

    g; g,             Jump to previous or next edits
    

    \#           Search word under cursor

    g# g*        Last occurence or first occurence of the word under the cursor

    ''           Last cursor position

    "1p "2p "3p  Paste the n line deleted
    

## Ranges

    :s/old/new/g       Changes all old to new in the current line

    :11,15s/old/new/g  Changes lines 11 to 15 inclusive

    :%s/old/new/g      Changes all lines


    .       Current line        :.w single.txt

    $       Last line           :$s/old/new/g

    1       First line          :1s/old/new/g

    1,2     Line one to two     :1,2s/old/new/g


    :'a,'bd              Delete lines from mark a to mark b, inclusive

    :.,'bd               Delete lines from the current line to mark b, inclusive

    :'a,'bw file.txt     Write lines from mark a to b to file.txt

    :'a,'bw >> file.txt  Append lines from mark a to b to file.txt

## Command mode 

    :ny          Copy line number n

    :.tn         Copy at line number n

    :1,5tn+      Copy range of lines first lines after line n

    :1,5d        Delete range of lines

    :3,6m.       Move range of lines below cursor

    :6t.         Copy line at current line

    :78,83join   Join range of lines together

    :earlier 5s  Go back in time

## Pattern matching commands

    n  Next matching search pattern

    N  Previous matching search pattern

    *   Next whole word under cursor

    \#   Previous whole word under cursor

    g*  Next matching search (not whole word) pattern under cursor

    g#  Previous matching search (not whole word) pattern under cursor

    :/search/d             Search and delete line found

    :/search/y             Search and yank line found

    :/search1/,/search2/d  Search and delete lines with multiple patterns

    :%s/target/\=@0/g      Replace target with what is yanked


    :g/href/d              Delete all lines with pattern

    :v/pattern/d           Delete all lines that do not match a pattern. The commands shown are equivalent (v is "inverse").

    :g/lines/z#.3          Display context (5 lines) for all occurrences of a pattern.

    :g//                   List all the lines where the last search pattern is

    qaq:g/pattern/y A      Copy all lines matching a pattern to register 'a'.

    :g/pattern/normal @q   Run a macro on matching lines (example assuming a macro recorded as 'q')

## Copy and paste

    yy Y  Yank current line (say "first line").

    yiw   Yank inner word (copy word under cursor, say "first")

    viwp  Select "second", then replace it with "first"

    Vp    Select "second line", then replace it with "first line".

## Cut and paste without moving

    m{char}   Create a marker for a letter

    '{char}   Jump to the created marker for a letter

    d'{char}  Cut lines from the following location to the mark

    y'{char}  Yank lines from the following location to the mark

## Delete, copy and paste in register

    "add          Delete it to register a

    "Add          Delete it to the same register

    "Ad           Delete the entire range and append it to the same register

    "ap "aP       Paste the line from register a before of after the cursor

    "+p (or "*p)  Pastes the contents of the clipboard

## Moving lines 

    :.m 12    Move current line to after line 12

    :5,7m 21  Move lines 5, 6 and 7 to after line 21

    :m 'a     Move current line to after line with mark a

    :m 'a-1   Move current line to before line with mark a

## Macros
    qd      Start recording to register d

    ...     Your complex series of commands

    q       Stop recording

    qA...q  Append to a macro in register A

    @d      Execute your macro

    @@      Execute your macro again


    :reg    View all registers

    :reg a  View only what you have recorded into register a

    qqq     Empties register q

    qqq qq <commands> @q q record a recursive macro in register q

## Vim script

http://ricostacruz.com/cheatsheets/vimscript.html
