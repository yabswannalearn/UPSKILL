staging - pag pasok ng file sa envelope
commit - pag lagay sa mailbox

![[Pasted image 20250314235200.png]]


pwd - pang check anong directory ka
ls - pang check ng laman ng folder
cd - pag lipat ng directory
git init - pag gawa ng repo

### COMMITING
git status - pag check ng status ng repo
git add - pag add ng file
git add  . - pag ng lahat ng file
git commit -m "message" - pag commit ng files. -m ay para sa log message

### CHECKING LOGS
git log - pang check ng commits from newest to oldest; press q para ma exit
git log:
git log -(number kung ilang gusto mong lalabas lang)
git log filename
git log --since='Month Day Year' - para specific kung mula kelan
![[Pasted image 20250315082233.png]]
![[Pasted image 20250315082316.png]]

git log (yung hash ng commit) - para makita mo specific commit log

### CHECKING DIFFERENCES

git diff - difference ng versions
git diff (file) - para makita mga different version sa file na yun
git diff --staged - pag compare lahat ng staged files sa version sa last commit
![[Pasted image 20250315082954.png]]
head~1 = head-1, so kung third most recent, minus 2 mo
![[Pasted image 20250315083109.png]]

### RESTORING
![[Pasted image 20250315083815.png]]
![[Pasted image 20250315083828.png]]

git revert
git revert --no-edit HEAD - para di ma open yung text editor
git revert -n HEAD - babalik yung files sa staging area
git checkout - revert single file

git restore --staged (filename) - pang unstage ng file
git restore--staged - pag unstage all files
![[Pasted image 20250315084124.png]]

pwede mo gawin to sa vscode para ma connect sya sa  [[GITHUB]]