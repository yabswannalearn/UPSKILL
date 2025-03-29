`alisin mga parenthesis kapag gagamitin na`

git branch - makita ano mga branch nasa repo
git switch (branch name) - llipat ka ng branch
git branch (branch name)  - gagawa kang bagong branch
git switch -c (branch name) - gagawa tas llipat ka sa branch na yun

### comparing branches
git diff (first branch) (second branch) - pag ccompare mo dalawang branches


### modifying branches
git branch -m (current name of branch) (new name of branch) - ma rerename yung branch
git branch -d (branch name) - deletion of branch
git branch -D (branch name) - ddelete mo yung branch kahit di kapa nag merge
![[Pasted image 20250315092043.png]]

### merging branches

punta ka muna sa destination branch
![[Pasted image 20250315092746.png]]
git merge (yung gusto mong i merge) (destination ng mmerge mo) - single line of command para pag wala ka sa destination branch

# conflicts
nano (filename) - open mo yung file

![[Pasted image 20250315093227.png]]![[Pasted image 20250315093343.png]]

# remotes
git clone (path) - pag clone ng  local repo
git clone (url) - pag clone ng github repo
git remote - para makita yung remote
git remove -v - more information sa remote
git remote add (name) (url) - ggawa ka ng remote na may name na

![[Pasted image 20250315094202.png]]
basically remote is a repo in online cloud services like github and gitlab or any server

### pulling from remotes
git fetch (remote name) - maffetch lahat ng branches
git fetch (remote name) (branch name) - specific branch lang ma ffetch
git merge origin - pa mmerge origin sa main
git pull origin

![[Pasted image 20250315095555.png]]

### pushing to remote
git push origin (filename)
git push (remote) (filename)
mag pull ka muna bago ka makapag push


this is for [[GITHUB]]
