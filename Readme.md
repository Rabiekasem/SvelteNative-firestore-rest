# svelte native firestore
this is a simple App for ios/android that connects to firebase/firestore with fetch call to the build in REST API.

it uses the <a href = "https://svelte-native.technology/docs"></a>
framework to build a native app. svelte-native is build on top of <a href="http://nativescript.org">Nativescript</a>, so you need to go through the setup guide there in order to install the TNS CLI tools.

## set up 
```html
npm install
the run [ios/android]
```

## project structure
this is a single page app. everything is handled in app/App.svelte.this file..
-fetches data from firestore in the svelte onMount function
uses a <a></a>