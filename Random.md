“When android command isn’t recognized” 
export PATH=${PATH}:/Users/btholmes/Library/Android/sdk/platform-tools:/Users/btholmes/Library/Android/sdk/tools

“TO LIST DEVICES” 
adb devices 
add kill-server
adb start-server

“TURN ON DEVELOPER MODE IN PHONE” 
Settings-about-(tab build number 7 times) 

“TO DEPLOY ONTO PHONE” 
ionic run android 

“TO CONFIGURE TABS BAR AT BOTTOM FOR ANDROID PHONE” 

.config(function($stateProvider, $urlRouterProvider, $ionicConfigProvider) { 
$ionicConfigProvider.tabs.position('bottom'); 

$stateProvider

.state('tab', {
url: "/tab",
abstract: true,
templateUrl: "templates/tabs.html"
})


“FIREBASE” 
sudo npm install firebase —save (In project)
—Load Firebase script, then angular stuff, and angularFire very last


first brew install tor
create file tor.sh below
chmod +x tor.sh 
$ tor.sh
________________________________________________________________________________
#!/usr/bin/env bash

# 'Wi-Fi' or 'Ethernet' or 'Display Ethernet'
INTERFACE=Wi-Fi

# Ask for the administrator password upfront
sudo -v

# Keep-alive: update existing `sudo` time stamp until finished
while true; do sudo -n true; sleep 60; kill -0 "$$" || exit; done 2>/dev/null &

# trap ctrl-c and call disable_proxy()
function disable_proxy() {
sudo networksetup -setsocksfirewallproxystate $INTERFACE off
echo "$(tput setaf 64)" #green
echo "SOCKS proxy disabled."
echo "$(tput sgr0)" # color reset
}
trap disable_proxy INT

# Let's roll
sudo networksetup -setsocksfirewallproxy $INTERFACE 127.0.0.1 9050 off
sudo networksetup -setsocksfirewallproxystate $INTERFACE on

echo "$(tput setaf 64)" # green
echo "SOCKS proxy 127.0.0.1:9050 enabled."
echo "$(tput setaf 136)" # orange
echo "Starting Tor..."
echo "$(tput sgr0)" # color reset

tor

________________________________________________________

Configure network settings by going to System preferences-proxies-click Socks type 
localhost as host, and whatever port is configured in browser. 

DEEP INTO THE ABYSS ________________________________________________________

Download and install TOR Browser Bundle: https://www.torproject.org/proje...

TOR Browser Bundle is a browser configured to use the TOR relay network, which anonymizes your connection through a distributed set of relays to prevent someone from learning your physical location and allows you to use sites which are blocked.  People use it to prevent websites from tracking their IP, or people in China use it get around the Great Firewall, for example.  The browser component is actually built using the Firefox codebase, so if you have used Firefox you will find it pretty familiar.  It comes properly configured and won't install any malware or cruft on your computer, as it is written and maintained by freedom fighters, not some large corporation.

Once you have TOR installed, open up the TOR browser, and go here:

http://kpvz7ki2v5agwt35.onion/wiki/index.php/Main_Page

You'll probably want to bookmark that in your TOR browser, unless you want to type in that URL each time.

SEARCH ENGINE 
Duck Duck Go
https://3g2upl4pq6kufc4m.onion/
ONION URLS
http://32rfckwuorlf4dlv.onion/

SAFETY ____________________________________________________________

1. Dont trust anyone out there in the deep web.

2. COVER your webcam using tape.

3. Never download any files or software from deep web.

4. If you want some extra protection (or maybe) , type "about:config" in the address bar, scroll down to "Javascript_enabled" and change the value from "true" to "false"

5. Don't use Utorrent or any other torrenting services while surfing on the deep web.

_____________________________________________________________________________________

DATES FOR ROOM RESERVATION

1/11/17, 1/18/17, 1/25/17, 2/1/17, 2/8/17, 2/15/17, 2/22/17, 3/1/17, 3/8/17, 3/15/17, 3/22/17, 3/29/17, 4/5/17, 4/12/17, 4/19/17, 4/26/17, 5/3/17, 5/10/17         
