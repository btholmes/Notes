FOR SIGNING IN WITH FACEBOOK 
This is probably the best tutorial for setting it up with Ionic2
https://ionicthemes.com/tutorials/about/ionic2-facebook-login
source code: https://github.com/ionicthemes/ionic2-facebook-login

	https://developers.facebook.com/docs/apps/register
Follow link to learn how to set this up with firebase. It?s in firebase under Authetication-signedIn

	https://github.com/fuffenz/ionic2-native-facebook-login
That github link has a working demo of sign in with facebook and shows how to install the cordova plugjns 
	cordova plugin add cordova-plugin-facebook4 --save --variable APP_ID="123456789" --variable APP_NAME="myApp"

cordova plugin add --save cordova-plugin-inappbrowser

cordova plugin add --save cordova-plugin-whitelist

ionic platform add android 

npm install 
ionic build android
ionic run android   


Ionic 2 Angular 2 Scotch.io NOTES (not done)
Ionic to  run on phone: 
	adb devices
	ionic platform android
	ionic build android
	ionic run android

Basic Ionic Commands: 

Ionic serve (to test in browser)

Ionic g page users

https://scotch.io/tutorials/build-a-mobile-app-with-angular-2-and-ionic-2#getting-github-users

-In user-details.html 
	The user?.property just tells angular that users may be null initially, so that an undefined error is not thrown.


Ionic 2 Angular 2 Firebase 3 NOTES
https://javebratt.com/ionic-2-firebase-3-week-1/


Commands to start

Ionic start name blank --v2
cd name
?	
o	ionic start creates the app.
o	eventTutorial is the name we gave it.
o	blank tells the Ionic CLI you want to start with the blank template.
o	--v2 tells the Ionic CLI you want to create an Ionic 2 project instead of an Ionic 1 project.
?	Third, you?ll navigate into the new eventTutorial folder, that?s where all of your app?s code is going to be.

1.)	First, we?ll need to update @ionic/app-scripts to use the latest version, since that?s the one with Webpack support, meaning it works with Firebase out of the box, you won?t have to create custom builds.

npm install @ionic/app-scripts@latest ?save-dev

2.)	Install Firebase 
npm install firebase --save


3.)	Create the pages and providers 
ionic generate page NameName
	--NOTE even though you type NameName, it creates like name-name inside pages directory. Each generated page comes with a .html, .ts, and .scss file

4.)	Generate the Providers ? file where will store the functions we share in our code. That way you can call it from anywhere in the app. 

ionic generate provider EventData

5.)	Import all new pages into app.module.ts, and add by names to declarations and entryComponents

6.)_ Add corodova extensi�n to be able to Access phones camera

ionic plugin add cordova-plugin-camera



NOW AUTHENTICATION

1.)	Go to app.component.ts and initialize firebase
Import firebase from ?firebase?; 

Then initialize it in the constructor also with the api information you get from firebase.com, have to create a new project for the database

	firebase.initializeApp({ 
apiKey: "", 
authDomain: "", 
databaseURL: "", s
torageBucket: "", 
messagingSenderId: "" 
});

also.. 

change @component to 
template: '<ion-nav [root]=?rootPage?></ion-nav>'
	change rootPage = HomePage to 
rootPage = any; 
	




2.)	Need to import homepage and  loginpage, also add ,NgZone to Component Import, create zone:NgZone variable before constructor, and create an auth observer inside constructor.
 
	firebase.auth().onAuthStateChanged((user) => { 
this.zone.run( () => { 
if (!user) { 
this.rootPage = LoginPage; 
} else { 
this.rootPage = HomePage; 
} 
}); 
});


3.)	Go to AuthData provider (This will communicate firebase authentication with Ionic) 

	Import firebase here also with/
Import firebase from ?firebase?
	Add two variable above constructor
public fireAuth: any;
public userProfile: any; 
	Create firebase references inside the constructor 
this.fireAuth = firebase.auth(); this.userProfile = firebase.database().ref('/userProfile');
	

	

4.)	Now create the login, logout, resetpassword, and signup functions

loginUser(email: string, password: string): any { 
return this.fireAuth.signInWithEmailAndPassword(email, password); }

signupUser(email: string, password: string): any {
  return this.fireAuth.createUserWithEmailAndPassword(email, password)
    .then((newUser) => {
      this.userProfile.child(newUser.uid).set({email: email});
    });
}

resetPassword(email: string): any { 
return this.fireAuth.sendPasswordResetEmail(email); 
}


logoutUser(): any { 
return this.fireAuth.signOut(); 
}

NOW LAYOUT FOR THE PAGES BEING USED 

1.)	login page
-add color=?primary? as attribute to ion-navbar

	Everything for ion-content is page 21 of pdf. 

