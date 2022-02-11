Movement
========

| vim           |     |
| ------------- | --- |
| `diw` / `daw` | delete word |
| `H / M / L`   | jump to the top / middle / bottom of the page |
| `ge` / `gE`   | jump to the end of previous word |
| `g;` / `g,`   | movement in the changelist |
| `g0` / `g$`   | move to the beginning / end of display line (not real line) |
| `+` / `-`     | down/up lines, on the first non-blank character |to 
| `{number}\|`  | to column #num |
| `(` / `)`     | sentences |
| `{` / `}`     | paragraphs |
| `%`           | to a reverse bracket |
| `*` / `#`     | find the *exact word* forward/backward + movement `n` / `N` |
| `g*` / `g#`   | find a *substring* forward/backward |
|               |    |
| `]]` / `[[`   | jump to { / } in the first column (top => left [, bottom => right ]) |
| ``` `] ```    | jump to the last character of the previously changed or yanked text |


```
SCROLLING:
zz		scroll to the middle
zt		scroll to the top
zb		scroll to the bottom

NORMAL MODE - others:
guu / gUU	to lowercase / uppercase
~		change case
C-i / C-o	move to previous/next cursor position 
ga		show numeric code of the character
x / X		delete the character at / before the cursor position
J / gJ		join lines with / without a space
q:		show list of last commands (it's not :q)
q/		show list of last searches
>i{		indent inside current set of curly braces

gq		format lines, e.g. apply 'textwidth' option

INSERT MODE:
gi		insert at last insert point
gp / gP		paste and stay at the end
:put		paste always as a block
C-r a		paste the register 'a'
C-r = 10*10	calculates 10*10
C-t		>> for the current line
C-d		<< for the current line

C-h		= backspace
C-w		delete one word
C-u		delete to the beginning of line

C-n/C-p		previous/next default completion
C-x C-f		File path
C-x C-l		Line

C-o		+ norm. command - v insert modu umoznuje spustit jeden norm. command

C-k a:		ä, ¼ ... (:h digraphs, :h digraph-table)


VISUAL MODE:
o		go to the other end of the highlighted text
O		move to the other corner in the same line
gv		select previously selected block

REPLACE/VREPLACE MODE:
R		REPLACE mode - <tab> is a single char
gR		VREPLACE mode - <tab> is edited as a multiple spaces

COMMAND MODE:
C-d		show autocomplete values
@:		repeat last command
C-r C-w		copy the word under cursor to command line

:pwd		print working directory
:e.		Ex for current pwd
:Ex		Ex for the directory of the active buffer
:V / Sexplore	Ex in vertical / horizontal split window

REGISTERS:
"0		yank only
"[1-9]		history registers
"[a-z]		named registers
"[A-Z]		same as "[a-z]" but with appending
"/		current search pattern
":		last : command
"-		small delete
"=		expression register
".		last inserted test
"%		filename of the current buffer
"+ / "*		system clipboard / [Linux: MMB, Windows: system] clipboard
"_		/dev/null register (e.g. for deleting)
""		unnamed register (used when no register provided)

BUFFERS
:bd		buffer delete
:b#		go to previous buffer

WINDOWS (:h windows)
C-w v / s	vertical / horizontal split
C-w c		close split
C-w x		switch windows
C-w o		this is only window (removes other windows)
C-w hjkl	move to a window
C-w p		move to the previous window
C-w w		move to the next window
C-w =		all windows have the same size
C-w HJKL 	move the current window
C-w T		move window to a separate tab
:split <file>	open <file> in a new split

q/		the list of last search terms
q:		the list of last used commands

MARKING:
:marks		the list of marks
ma		mark position 'a' (lowercase - local to a buffer)
mA		mark position 'A' (uppercase - global, persisted)
'a / `a		go to line 'a' / go to position 'a'
``		position before the last jump within current file
`.		location of last change
`^		location of last insertion
`[		start of last change or yank
`]		end of last change or yank
`<		start of last visual selection
`>		end of last visual selection

DIFF:
]c		next difference
[c		previous difference
do		diff obtain
dp		diff put
zo		open folded text
zc		close folded text
:diffupdate	re-scan the files for differences
C-w w		toggle between the diff columns
:set diffopt+=iwhite
		to avoid whitespace comparison

SEARCH
* [https://learnbyexample.gitbooks.io/vim-reference/content/Regular_Expressions.html]
* [http://vimregex.com/]
/ ?		without any text + <CR> = repeat last search
/abc<C-r><C-w>	put the currently highlighted word into the cmd line
/\v...		regular expressions => all symbols have a special meaning, use \ to escape
/\V...		verbatim search => no symbols have a special meaning
			except: / or ? and \ - these needs esc char '\' each time (Tip 79)
/.../e		find ... and move the cursor to the end (also possible /... + //e)
\w		word characters => a-z, A-Z, 0-9, _
\W		everything except word characters
<word>		< / > boundaries of \w+ => find words only (see * cmd)
X\zs...\zeY	search for X...Y but highlight ... only
			/\v"\zs[^"]=\ze" => find "abc", highlight abc only
q/		open a separate window for search + <CR> to search
:%s//.../g	substitute last searched pattern

MULTIFILE SEARCH
:vim[grep] /pattern/g WHERE
WHERE: *, **, ## (files in args), **/*.js (recursive)
:cnext, :cnfile, :copen, :clist

FOLDS
zfi}		create fold (zf) in {...}
zo / zc / za	open / close / switch fold

ASCII/UNICODE VALUE OF THE CURRENT CHARACTER
ga
:ascii

MULTIPLE CURSORS REPLACEMENT
1. go to word to change
2. *``		find all other occurrences and return back to that word
3. cgn		select next highlighted word (don't move if already there), visually select it and change
4. write a new text + ESC
5. hitting . causes moving to next highlighted selection and changing

ABBREVIATIONS
:ab fsf Free Software Foundation
when writing and don't want to expand fsf, write fsf<CTRL-Q><next char>

TABS => SPACES
:set tabstop=20
:set expandtab
:retab

RUN A MACRO FOR SELECTED LINES
select lines
:'<.'>normal @a

SPELL CHECK
:set spell spelllang=en
]s	to next error
z=	when on a misspelled word, get some suggestions
zg	mark a misspelled word as correct
zw	mark a good word as misspelled

TERMINAL
C-w w	leave the terminal window
C-\ C-n	to normal mode
C-\ N	to normal mode
i / a	activate terminal again
C-w :bd! close the terminal

tnoremap <Esc> <C-\><C-n>:q!<CR>
```

MULTIPLE FILES
| ``args c:\path\**\*.java`` | open all java files recursively |
| ``argdo normal @w``        | execute macro `w` on each opened file |


Links
=====
[:help usr_toc.txt](https://vimhelp.org/usr_toc.txt.html)

Regular expressions
-------------------
- http://vimregex.com/
- https://learnbyexample.gitbooks.io/vim-reference/content/Regular_Expressions.html
