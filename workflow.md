## Initialization (only do once)
	git config --global user.email youremail@example.com  
	git config --global user.name "Your name"  
	git clone <repor link>  
	git checkout -b <your branch>  
	(Ex: git checkout minhanh)  

## Start working
	git pull origin main  
	.. working...  

## Finish working (Gonna turn your lap off)
	git add -A  
	git commit -m "Your mesages"  
	git pull origin main  
	(If there are CONFLICTS, resolve the conflicts)  
	git push origin <your branch>  

## Resolve conflicts
1. Delete ====, ||| HEAD
2. Modify the code, test the program again.
3. Do all the steps in the Finish Working section
