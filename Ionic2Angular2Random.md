IONIC 2 ANGULAR 2
Ionic command not found 
npm ls (shows where npm is installed) 
npm config get prefix (should be usr/local)
Can set with npm config set prefix
Also npm root ?g should return (/usr/local/lib/node_modules)
Can set with npm config set prefix /usr/local

Could also try uninstall and reinstall node with (brew uninstall node) (brew install node) 
brew uninstall node; 
brew prune; 
rm -f /usr/local/bin/npm; 
rm -f /usr/local/lib/dtrace/node.d; 
rm -rf ~/.npm;

brew install node; 
which node #=> /usr/local/bin/node 
export NODE_PATH='/usr/local/lib/node_modules' # add to bashrc if not already there

NODE ALREADY INSTALLED JUST NOT LINKED after (brew install node command)

(Sudo) brew uninstall node 
brew update 
brew upgrade 
brew cleanup 
brew install node 
sudo chown -R $(whoami) /usr/local 
brew link --overwrite node 
brew postinstall node

no such file or directory, rename '/usr/local/lib/node_modules/.staging/ansi-392b32ed'
Just use sudo npm uninstall ionic ?g 
Sudo npm install ?g ionic
