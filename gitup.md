initial
```git
git init
git add .
git commit -m "first commit here"
git branch -M main
git remote add origin https://github.com/penteler/name.git
git push -u origin main

```
undo last commit `git revert head`

`git stash` undo stash `git stash pop`
to cherrypick
`git cherry-pick 4tigsrt`
first few letters of the sha
exit without saving `:q!` and `wq` to save changes before q.
```vim ~\FolderOrFile is the same as C:\Users\username\FolderOrFile. If the cursor appears to be directly behind a character in cmd or PowerShell then it is on that character.
vimtutor
:sav fil
vim fil
vim file.txt

```
The percentage of the file that lies above and behind the cursor is displayed at the bottom right. This must have served a purpose similar to the scroll bar to give the readers an estimate of the size of the file that they've been through and the rest of it which lies ahead. So far it doesn't seem like you can use it for scrolling itself but you could just hold the up/down/j/k/h/l/right/left/pageup/pagedown key while keeping an eye on the percentage. Next to this there's the line number and number of characters to the left of the cursor `52,16` or it can be like `54,2-16` if the tab size it 8 for the 54th line 2nd tab and 16 spaces or it can be `57,2-9` if theres 1 tab of size 8 followed by one space behind the cursor. Some times there are no characters or spaces `56,0-1` 56th line 0 tabs and one space you canot move left or right here you can skip over the line by going up or down. If you were to select multiple characters with the cursor using the mouse you will see `-- VISUAL --` written in all caps in the bottom left and to the right of that and to the left of the line number you'll see the number of characters that have been selected in a line but if you select multiple lines it will show you the number of lines selected instead. If you use `:w` to save/write this will appear in the bottom left `"fil" [unix] 972L, 33600B written` fil is the file name I'm assuming it ends with the number of bytes written.
This may appear when you undo `change; before #22 12 seconds ago ` and if you redo it'll say after instead of before.
If you were to save changes in a file in one istance of Vim then you might see this in the sell running a readonly instance of Vim:
```W11: Warning: File "fil" has changed since editing started
See ":help W11" for more info.
[O]K, (L)oad File, Load File (a)nd Options:                                                                        
```
motions for the `d` operator:
w - the word following the cursor including the space
e - the same as above but it will spare the space
$ - this will remove every character upto the end of the line gobbling up every period, comma, full stop.
Basically the only differnce that I can tell bettween e and w is that w will not spare the space and e will spare it from being deleted so using these motions without an operator like d you'll move the cursor to the beging of the next unaffected word and with e you'll move to the end the affected word. Use it with d and you'll delete everything upto the begining of the next word excluding the first character but with e you'll remove everything upto and including the end of the word