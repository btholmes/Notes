# Useful Shell Commands 

General 
	*find . -type f -name '*.o' -delete
	
Git Commands 
	*git clone "name"
	*git add . 
	*git commit 
	*git push (If you get error try)
	*git push origin master 
	
	To solve git status --porcelain failed in 'directory'
		1. Have to delete all the .git files located in the 'directory'
		2. Run this command : 
			*find . -name ".git*" -exec rm -R {} \;
	
	A blackened unclickable folder in Github represent an old repo that wasn't removed locally properly. 
		1. git init
		2. git remote add origin git@github.com:btholmes/Website
		3.  
