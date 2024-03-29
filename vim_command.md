## normal mode

|command|description|
|-----|-----|
|`:tabedit <file>`|open a tab for `<file>`|
|`[i]gt`|go to `[i]`th tab|
|``:e `=<command>` ``|edit the output of `<command>`|
|`:e #[n]` \| `CTRL-^`|Edit the alternate file (mostly the previously edited file)|

## use tags (requires tag generators, such as ctags)

## vim tutor?
```vim
:q!
:help

// save file
:w FILENAME
v // visual selection

// merge file
:r FILENAME

// move cursor
[hjkl]
[\d][we$]

// delete
x
d[\d][we$]
[\d]dd

// undo
u
U
Crtl r

// open a line
o
O

// insert mode
i

// append mode
a
A

// put previously deleted text after cursor
p

// replace
r[\w]
R

// change until the end of word
ce

// change text
c[\d][we$]

// location in file
Ctrl g
gg
[\d]G

// search
/ // forward search
n // search for the same phrase
N // search for the same phrase in the opposite direction
? // backward search
Ctrl o // go backward
Ctrl i // go forward

// find matching )]}.**
%

// substitute
:s/old/new
:s/old/new/g
:#,#s/old/new // substitude between lines
:%s/old/new/g // substitude in whole file

// set option for substitute and search
:set ic
:set hls is
:set noic


// copy paste
y
p
```
