:sp - open horizontal split
:vsp - open vertical split
:tabnew - open a new tab
:close - close the tab 
<leader><cr> || :noh - stop highlighting last search
<leader>bd || :Bclose - close current buffer
<leader>ba - close all buffers
<leader>cd - switch to the directory of the open buffer
<leader>mb - make current window bigger by 10 columns/rows
<C-w>> - make vertical split bigger by 1
<C-w>< - make make vertical split smaller by 1
<C-w>= - make vertical slits the same size
<leader>mvb || :vertical resize +10 - make vertical split bigger by 10
<leader>mvs || :vertical resize -10 - make vertical split smaller by 10
<leader>mhb || :resize +10 - horizontal bigger by 10
<leader>mhs || :resize -10 - horizontal smaller by 10
<leader>e - edit the vim config file
<leader>c - edit the cheatsheet file
<leader>q - open a scratch buffer
:Lorem - put in a paragraph of lorem ipsum at the cursor
<leader>jt - format json using python json.tool
<leader>b || <leader>be - open the buffer explorer
<leader>bv - open the buffer explorer in vertical split
<leader>bs - open the buffer explorer in horizontal split
<leader>tt - toggle the tagbar
<leader>tags - basic tag generation using ctags
:bw || :bd - close buffer and window
:BW || :BD - close buffer but leave window
<leader>ig - switch on indent guides
<leader><leader><motion> - switch on easymotion guides (where <motion> is any motion command)
vir - visually select inside the block
var - visually select inside and outside of the block
<c-a> - increment date/time/number
<c-x> - decrement date/time/number
:YRShow - show yankring window
<C-w>_ - maximize current window/split
<C-w>+ - increase horizontal split height
<C-w>- - decrease horizontal split height
:noautocmd lvimgrep /hello/gj **/* - grep through all files recursively for 'hello' and put results in location list local to current window
                                   - the noautocmd switches off autocommands during search to make the grep much faster (but will disable highlighting if you jump to first match automatically)
                                   - the g option will return all matches instead of just one per line
                                   - the j option will not jump to the first match automatically
:lw || :lopen - open the location list for current window
:cw || :copen - open the quickfix list



Movement Commands
--------------------------
h                        - left
j                        - down
k                        - up
l                        - right
$ || -                   - go to end of line
^ || 0                   - go to start of line
gg                       - go to start of file
G                        - go to end of file
H                        - cursor to top of screen
M                        - cursor to middle of screen
L                        - cursor to bottom of screen
:5 || 5G                 - go to line 5
w                        - next word start
b                        - previous word start
e                        - next word end
ge                       - previous word end
W                        - next WORD start
B                        - previous WORD start
(                        - next sentence
)                        - previous sentence
{                        - next paragraph
}                        - previous paragraph
n|                       - nth column of current line
%                        - jump ot matching bracket (),{},[]
<C-e>                    - scroll up 3 lines
<C-y>                    - scroll down 3 lines
<C-f>                    - move up one screen
<C-b>                    - move down one screen
m<char>                  - mark current position where <char> is [a..Z]
'c                       - go to mark
'.                       - last edited line
:marks                   - print all marks
:jumps                   - print all jumps
n<C-o>                   - go to nth older position in jump list, scroll forward through jump list
n<C-i>                   - go to nth newer position in jump list, scroll backward through jump list
g;                       - jump backwards through the changelist
g,                       - jump forwards through the changelist
f<char>                  - move forward to first occurence of <char> where <char> is any character
t<char>                  - move forward before the first occurence of <char> where <char> is any character
F<char>                  - move backward to first occurence of <char> where <char> is any character
T<char>                  - move backward to right after the first occurence of <char> where <char> is any character
;                        - repeat the f,t,F,T command in the forward direction
,                        - repeat the f,t,F,T command in the backward direction


Insert Commands
--------------------------
i - enter insert mode before cursor
I - go to start of line and enter insert mode
a - enter insert mode after cursor
A - go to end of line and enter insert mode
ea - enter insert mode at the end of current word
o - blank line below
O - blank line above
<ESC> || <C-c> || <C-[> - exit insert mode
r - replace character under cursor
J - join line below to the current one
s - delete character and substitute text
cw - replace from cursor to end of word
cc - replace from cursor to end of line
x - delete char under cursor
X - delete char before cursor
dw - delete from cursor to end of word
dd - delete current line
yw - copy from cursor to end of word
yy - copy current line
p - paste after
P - paste before
:x,yd                  - delete lines x through y
"ayy - copy line into register a
"ap - paste from register a
~ - switch case of char under cursor
g~<move command> - switch case of movement command e.g. g~w for word
gu<move command> - lowercase text of movement command
gU<move command> - uppercase text of movement command
<C-w>                  - backspace over a word while in insert mode
<C-o>                  - enter normal mode for one command while in insert mode
<C-u>                  - delete to beginning of indent while in insert mode
<C-x><C-l>             - line completion while in insert mode
<C-y>                  - copy letter above the cursor
<C-e>                  - copy letter below the cursor
<C-x><C-o>             - omnicompletion
< C-r">                - paste from default register in insert mode (probably can substitute the " 
                         to any other register to paste from that one)

Search/Replace Commands
---------------------------

* /,?                    - search forward, backward
* n,N                    - repeat search in same direction, opposite direction
* :s/old/new/g           - replace only on current line
* :%s/old/new/g          - replace old with new in file
* :%s/old/new/gc         - replace old with new in file with confirmation
* *, #                   - search for next instance of word under cursor, previous instance
* :%s/\<foo\>/bar/gc     - change only whole words exactly matching 'foo' to 'bar'; ask for confirmation
* :%s/foo/bar/gci        - change each 'foo' (case insensitive) to 'bar'; ask for confirmation
* :g/^baz/s/foo/bar/g    - change each 'foo' to 'bar' in each line starting with 'baz'
* :%s//bar/g             - replace each match of the last search pattern with 'bar'
* :%s/foo/<c-r><c-w>/g   - replace each occurrence of 'foo' with the word under the cursor
* :%s/foo/<c-r><c-a>/g   - replace each occurrence of 'foo' with the WORD under the cursor
* :%s/foo/<c-r>a/g       - replace each occurrence of 'foo' with the contents of register 'a'
* :%s/<c-r>a/bar/g       - replace all occurrences of the text in register 'a' with 'bar'

Buffers And Split Windows
---------------------------
* :e file                - open file in new buffer
* :bn, :bp, :b3, :bd     - next buffer, previous buffer, buffer number 3, close buffer/file
* :sb3                   - buffer number 3 split window horizontally
* :split                 - split current window
* :new file              - open new file in split window
* <C+ws>                 - Split windows
* <C+wv>                 - Split windows vertically
* <C-w>q                 - close currently selected split window
* <C-w>_                 - maximize current window
* <C-h,j,k,l>            - move between split windows

Pathogen
--------------------------
* :Helptags - generate help doco for all directories in in runtimepath (if they have any)

TailMinusF
--------------------------
* :Tail filename - tail -f the file in a preview window
* :pclose - close the preview window

vim-rails
--------------------------
* :Rtags - generate tags for current rails project (needs exuberant ctags installed)
* :Rlog - crack open the log file (tail -f style)
* gf,C-wgf - based on cursor context edit file under cursor (current tab or new tab)
* :A,:AE,:AS,:AV,:AT,:AD - edit alternate file to current file (e.g. test file)
* :R,:RE,:RS,:RV,:RT,:RD - edit related file to current file
* :Rcontroller,:Renvironment,:Rfixtures,:Rfunctionaltest,:Rhelper,:Rinitializer,:Rintegrationtest,:Rjavascript,:Rlayout,:Rlib,:Rlocale,:Rmailer,:Rmetal,:Rmigration,:Rmodel,:Robserver,:Rplugin,:Rschema,:Rspec,:Rstylesheet,:Rtask,:Runittest,:Rview <name> - edit current relevant file, or relevant file with name			
* :[range]Rake {targets},:[range]Rake! {targets} - run specified rake targets, has sensible defaults (with the bang won't open quickfix window)
* :Rscript {script} {options} - run script, e.g. :Rscript console to run up the console

* with surround adds the following surroundings
=	<%= ^ %>
-	<% ^ -%>
#	<%# ^ %>

vim-fugitive
--------------------------
:Git [args] - run arbitrary git command
:Gstatus    - Bring up the output of git-status in the preview window.  The following maps, which work on the cursor line file where sensible, are provided:
    <C-N> next file
    <C-P> previous file
    <CR>  |:Gedit|
    -     |:Git| add
    -     |:Git| reset (staged files)
    C     |:Gcommit|
    cA    |Gcommit| --amend --reuse-message=HEAD
    ca    |Gcommit| --amend
    D     |:Gdiff|
    ds    |:Gsdiff|
    dp    |:Git!| diff (p for patch; use :Gw to apply)
    dp    |:Git| add --intent-to-add (untracked files)
    dv    |:Gvdiff|
    O     |:Gtabedit|
    o     |:Gsplit|
    p     |:Git| add --patch
    p     |:Git| reset --patch (staged files)
    q     close status
    R     reload status
:Gcommit [args] - wraps git commit, commit message in split window
:Glog [args]    -  Load all previous revisions of the current file into
                        the quickfix list.

MORE TO LOOK AT, but need to try them all out to understand what they do!!!

vim-surround
--------------------------
* ds",dst - delere specified surround (t is if it is an xml tag)
* cs"',cs"<q>,cst<p> - change surround from one to the other,or into a tag, or a tag into another tag
* ysiw) - insert surround, i.e. you surround vim motion with the specified
* ySiw) - same as above but indent surround text and place the chars on separate lines
* yss - surround current line
* ySS - indent surround text and place surround chars on separate lines
* vS - in visual mode simply pressing S allows you to specify surrounds, in linewise the text is indented and surrounds are on separate lines, in blockwise each line is surrounded
* Eight punctuation marks, (, ), {, }, [, ], <, and >, represent themselves and their counterparts.  If the opening mark is used, contained whitespace is also trimmed.  The targets b, B, r, and a are aliases for ), }, ], and > 

vim-cucumber
--------------------------

nerdcommenter
--------------------------
* ,c<space> - comment out current line, or current selection if in visual mode

nerdtree
--------------------------
* F2 - open nerdtree
* ma - add childnode
* mm - move current node
* md - delete current node
* mc - copy current node
* t,T - open in new tab, silently
* o,O - open/close node, recursively
* x,X - close parent of node, close all child nodes of current node
* p,P - go to parent, go to root
* C - change root to current dir
* u,U - move tree root up a dir, move tree root up but leave old root open
* r,R - refresh dir, refresh root
* m - show menu
* I - show hidden files
* q - close nerdtree window
* A - zoom nerdtree window

ack.vim
--------------------------
You obviously need to have ack installed

* :Ack[!] [options] {pattern} [{directory}] - search current directory for pattern, opens matches in quickfix window
* :AckAdd [options] {pattern} [{directory}] - same as Ack but append to current quickfix list
* :AckFromSearch [{directory}] - use pattern from previous search
* :AckFile [options] {pattern} [{directory}] - search for filename matching pattern

bufexplorer.zip
--------------------------
* ,be or ,bs or ,bv - open explorer in current windows, split or vsplit

Commands to use once exploring:

* <F1> - help information.
* <enter> or <leftmouse>, <shift-enter> - open buffer in current window, open in another tab
* d - delete the buffer under the cursor from the list
* R - toggles relative path/absolute path
* T - toggles to show only buffers for this tab or not
* f - toggles whether you are taken to the active window when selecting a buffer or not
* o - opens the buffer that is under the cursor into the current window
* q - quit exploring
* r - reverses the order the buffers are listed in
* s - order buffers by buffer number, file name, file extension, most recently used (MRU), or full path.
* t - opens the buffer that is under the cursor in another tab.
* u - toggles the showing of "unlisted" buffers.

Command-T
--------------------------
You need to build the C extension to make sure this thing works properly. You need to jump into the plugin directory, then:

rvm use system  #have to use the same ruby that Vim links against
rake make

* ,t - search for files

vim-ragtag
--------------------------
Using binding in insert mode at the end of line consiting of foo:

* <C-X>=  - foo<%= ^ %> 
* <C-X>+  - <%= foo^ %>
* <C-X>-  - foo<% ^ %>
* <C-X>_  - <% foo^ %>
* <C-X>'  - foo<%# ^ %>
* <C-X>"  - <%# foo^ %> 
* <C-X><Space> - <foo>^</foo>
* <C-X><CR>    - <foo>\n^\n</foo>
* <C-X>/       - Last HTML tag closed

vim-unimpared
--------------------------
* [a - |:previous| file in argument list
* ]a - |:next| file in argument list
* [A - |:first| file in argument list
* ]A - |:last| file in argument list
* [b - |:bprevious| buffer in buffer list
* ]b - |:bnext| buffer in buffer list
* [B - |:bfirst| buffer in buffer list
* ]B - |:blast| buffer in buffer list
* [l - |:lprevious| error in location list for current window
* ]l - |:lnext| error in location list for current window
* [L - |:lfirst| error in location list for current window
* ]L - |:llast| error in location list for current window
* [q - |:cprevious| error in quickfix list
* ]q - |:cnext| error in quickfix list
* [Q - |:cfirst| error in quickfix list
* ]Q - |:clast| error in quickfix list
* [t - |:tprevious| tag in matching tag list
* ]t - |:tnext| tag in matching tag list
* [T - |:tfirst| tag in matching tag list
* ]T - |:tlast| tag in matching tag list
* [e - exchange the current line with line above
* ]e - exchange the current line with line below
* [x{motion}, [xx, {Visual}[x - xml encode
* ]x{motion}, ]xx, {Visual}]x - xml decode
* [u{motion}, [uu, {Visual}[u - url encode
* ]u{motion}, ]uu, {Visual}]u - url decode
* [y{motion}, [yy, {Visual}[y - C string encode (i.e. backslash escape)
* ]y{motion}, ]yy, {Visual}]y - C string decode

snipmate.vim
--------------------------
ruby

eruby



taglist
--------------------------
* :TlistToggle - toggle tag list window
* p - preview current tag (don't jump the cursor to editor window)
* tab, backspace - jump through the various open files
* u - refresh tags for file
* -,+,*,= - close fold, open fold, open all folds, close all folds
* s - sort tags in different ways
* x - maximize or minimize tag window

vim-easygrep
--------------------------
* ,vv  - Grep for the word under the cursor, match all occurences, like 'g*'.
* ,vV  - Grep for the word under the cursor, match whole word, like '*'.
* ,va  - Like vv, but add to existing list.
* ,vA  - Like vV, but add to existing list.
* ,vr  - Perform a global search on the word under the cursor and prompt for a pattern with which to replace it.
* ,vR  - Like vr, but match whole word.
* ,vo  - Open an options explorer to select the files to search in and set grep options.

* :Grep [arg] - Search for the specified arg, like <Leader>vv.  When an ! is added, search like <Leader>vV
* :GrepAdd [arg] - Search for the specified arg, add to existing file list, as in <Leader>va.  When an ! is added, search like <Leader>vA

    The Above commands can additionally accept command switches:
    -r   Perform a recursive search
    -R   Perform a recursive search
    -i   Perform a case-insensitive search
    -I   Perform a case-sensitive search
    -m   Specify the number of matches to get

* :Replace [target] [replacement]
* :Replace /[target]/[replacement]/ - Perform a global search and replace.  
* :ReplaceUndo - Undoes the last :Replace operation.  
* :GrepOptions - Open the options explorer to set options.

vim-coffee-script
--------------------------
* :CoffeeMake[!] {opts}	
* :[range]CoffeeCompile [vertical] [{win-size}] - Shows how the current file or [range] is compiled to JavaScript. 
* :CoffeeCompile {watch} [vertical] [{win-size}] - The watch mode of :CoffeeCompile emulates the "Try CoffeeScript" live preview on the CoffeeScript web site. 
* :[range]CoffeeRun	Compiles the file or [range] and runs the resulting JavaScript, displaying the output.

vim-rake
--------------------------

zencoding.vim
--------------------------
* <C-y>, - expand zencoding abbreviation

examples:
html:xt>div#header>div#logo+ul#nav>li.item-$*5>a


Visual mode commands
--------------------------
* v,V,Ctrl-v - visual mode, linewise, block visual mode, mark lines then do command (such as yank or delete)
* o, O - move to other end of marked area, corner of block
* esc - exit visual mode
* aw,abb - mark word,umark word
* gv - restore previous selection
* i" - selects the contents of quotes.
* i( - select the contents of parens.
* i[ - selects the contents of square brackets.
* i{ - selects the contents of curly brackets.

Macros
----------------------
* qc, q - record macro to register where c is [a..Z], stop recording
* @c, 5@c - execute macro in register c, do it 5 times
* @@ - repeate previous @ command

Useful commands
----------------------------
* <ctrl-p>, <ctrl-n> - complete word based on words in buffer
* u, <ctrl-r> - undo,redo
* . - repeat last command
* :r file, :r! command - read file and insert after current line, exeute command and insert output below cursor
* :w filename - save to filename
* :sh - go back to shell, Ctrl-D to go back to vi
* !!pwd - execute pwd and insert output in file
* ctrl-a, ctrl-x - increment decrement number under cursor, next number on line
* "+yy, gg"+yG - copy line to system clipboard, copy whole file
* :w !sudo tee % - save the file even though opened in readonly mode without sudo
* :'a,'b !sort - sort lines between mark a and b 
* :%sort, :%sort!, :%sort u- sort whole file, in reverse, unique the lines
* V= - format visual selection
* gg=G,mzgg=G'z<CR> - format whole file, source code, format whole file and go back to where you were before
* == - indent line
* :wa, :xa - save all buffers, save and close all buffers
* :%y+ - copy entire file into clipboard
* q:, q/ - open command line history window, search hostpry window, can edit history commands and re-execute them (Ctrl-c twice to close window without executing anything)
* :grep -r CitySearch . --include=*.rb --include=*.log - recursively search for citysearch in the current directories only include .rb and .log files
* :cn, :cp, :clist - go to next match, go to previous match, list all matches
* :Vex, :Sex - browse file system in split window and take action on file (e.g. open a file)
* ,Enter - stop highlighting search results
* ,u - reload Minibufferexplorer window
* ,ss - switch on spellchecking
* ,t - launch fuzzy finder in current directory
* ,q - open a scratch buffer for scribbling
* ,nf - open current selected file in NERDTree
* C-^ - edit the previous file

Operators and Motions and Text Objecs
------------------------------------
* d,c,y - delete, change, yank operators
* iw, aw - exclusive and inclusive motion on a word
* yi" - yank everything between matching "
* ya[ - yank everything between and including matching [
* dis, dip - delete inner sentence, paragraph
* yit - yank everything between matching html tags

Spellchecking
------------------------------------
* ,ss - toggle spellchecking
* zg - add word to good words list
* ]s - next misspelt word
* [s - previous misspelt word

Ctags stuff
------------------------------------
* ctrl-] - go to tag under cursor
* ctrl-t - go back to where you were after having jumped to tag
* ctrl-w ctrl-] - open tag under cursor in a horizontal split
* ctrl-\ - open tag under cursor in a new tab
* ctrl-W c - close the currently open tab

Abbreviations
----------------------------------
* :ab, :iab - create abbreviation, works for insert mode only (e.g. :ab blah hello)
* :una abbrv - delete the abbreviation named abbrv
* :abc - delete all abbreviations

Folding
----------------------------------
* zfnj - creates a fold from the cursor down n lines.
* zo - opens a fold on the cursor.
* zc - closes a fold on the cursor.
* zj - moves the cursor to the next fold.
* zk - moves the cursor to the previous fold.
* zd - deletes the fold at the cursor.
* zE - deletes all folds in the document.
* zM - closes all open folds.
* zR - opens all folds.

Yankring
--------------------------------
* <C-p>,<C-n> - move forwards and backwards throught the yankring
