# Useful Shell Commands / Working with GitHub

## General
 * find location -name 'name.ext'
 * mdfind string (will find all the files with text "string" in them)
 * mdfind mysearch -onlyin "root locadtion" (Only looks in that one directory)
 * mdfind -name FileName
 * find ~ -iname "value*" (Finds anything in home directory with word "value" in it)
 * find ~ -iname "value*" | more  (If lots of results) 
 * echo "string" >> README.md
 * nano ~/.Profile (Put your export path statements here) 
 * nano ~/Bashrc (Put alias here so you can use from command line) 
	 
	
## Git Commands 
 * git clone "name"
 * git add . 
 * git commit 
 * git push (If you get error try)
 * git push origin master 
 * git stash 
 * git stash pop 
 
	

#### To solve git status --porcelain failed in 'directory'
 1. Have to delete all the .git files located in the 'directory'
 2. Run this command : 
    * find . -name ".git*" -exec rm -R {} \;

 1. To solve git status --porcelain failed in 'directory'
 * Have to delete all the .git files located in the 'directory'
 * Run this command : 
 * find . -name ".git*" -exec rm -R {} \;
	
#### A blackened unclickable folder in Github represent an old repo that wasn't removed locally properly. 
 1. git fetch

#### Create a bash script to make the github repository 
 1. create script.sh inside a file called my_scripts on the Desktop with this 
 
  			#!bin/bash
		        curl -u 'UserName' https://api.github.com/user/repos -d "{\"name\":\"$1\"}";
			git init;
			git remote add origin https://github.com/btholmes/$1.git;
			
 2. chmod 755 githubscript.sh
 3. nano ~/.profile;
 
			export PATH="$PATH:$HOME/Desktop/my_scripts" (to exit nano use)
			ctrl x (Then answer yes about saving press enter )
			
 4.  also do nano ~/.Bashrc 
			alias githubrepo="bash githubscript.sh"
 5. source ~/.bashrc ~/.profile; cd (to reload bash in termial) 
 6. Then use command githubrepo nameOfRepository
	
# The Ultimate Method for creating a repository and pushing code to it 
 * githubrepo name (Now it's created on github) 
 * mkdir where you want it 
 * switch into directory and run echo "# Website" >> README.md
 * git init 
 * git add . 
 * git commit -m "Initial Commit"
 * git remote add origin https://github.com/btholmes/Demo.git (This only needs to be done on the inital creation) 
 * git push -u origin master
	
	
## Setting up User login information for GITHUB 
 * ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
 * eval "$(ssh-agent -s)"
 * ssh-add -K ~/.ssh/id_rsa

## Add images to README 
 * ![Alt text](/relative/path/to/img.jpg?raw=true "Optional Title")

	
## Generating SSH keys
 * Check if you have one already with cat ~/.ssh/id_rsa.pub
 * If you don't have one, generate one with ssh-keygen -t rsa -C "btholmes@iastate.edu"
 * When prompted for location and file name just press enter
 * use this to change password ssh-keygen -p <keyname>
	
## Creating Branches in GitLab
 * git clone                   //clone what branch you want
 * git checkout -b new_branch  //this will create a new local branch
 * git push origin new_branch  //this will create a new origin branch
	
### Push branches to master
 * first get all changes in branch from git pull origin branchName
 * git checkout master
 * git pull origin master
 * git merge test
 * git push origin master
	
### Refusing to merge unrelated histories
 * git pull origin branchName --allow-unrelated-histories
	
	
### Generate Key for Login with Facebook 
	- **OSX**
	- keytool -exportcert -alias androiddebugkey -keystore ~/.android/debug.keystore | openssl sha1 -binary | openssl base64
	- **Windows**
	- keytool -exportcert -alias androiddebugkey -keystore %HOMEPATH%\.android\debug.keystore | openssl sha1 -binary | openssl base64
	
### Install Cordova Plugin for Facebook 
	- ionic plugin add cordova-plugin-facebook4 --variable APP_ID="123456789" --variable APP_NAME="myApplication"

## To list all processes running 
	ps -ax 
    lsof -i tcp:3000 
	killall (kills all processes)

## Find if port is in use 

    sudo lsof -i TCP:$PORT | grep LISTEN (replace $port with port number)

## For Angular2 error with cannot find hmr 

    sudo npm install @angularclass/hmr @angularclass/hmr-loader

## USE sftp to copy file from local to server

    sftp usrname@orgname.edu
    Enter password
    cd <directory where you want to transfer the file>
    put <name of file you want to transfer>
    
    
## Make Android Studio Run Faster 

	Add this to gradle properties 
	org.gradle.daemon=true
	
	Android -> Preferences -> Build, Execution, Deployment -> Compiler
	Check the Option -
	Compile independent modules in parallel (may require larger heap size)
	Set VM Options to :  -Xmx2048m -XX:MaxPermSize=512
