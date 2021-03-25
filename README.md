# Firebase
## Initialize firebase
const app = firebase.initializeApp({

  apiKey: "",
  
  authDomain: "",
  
  databaseURL:"" ,
  
  projectId:"" ,
  
  storageBucket:"" ,
  
  messagingSenderId:"" ,
  
  appId: ""
  
});


## Firebase Authentication
### onAuthStateChange
```javascript
firebase.auth().onAuthStateChange(callback to return an observable)
```

### Register email and password
```javascript
await firebase.auth().createUserWithEmailAndPassword(email, password)
```

### Sign in with email and password
```javascript
await firebase.auth().signInWithEmailAndPassword(email, password)
```

## Cloud Firestore
To use firebase cloud firestore, first you'll need to import firestore from firebase.
```javascript
import firestore from 'firebase/firestore';
```

- Connect to a collection:
````javascript
firestore.collection('books'); // returns a collection reference called books
```
- Connect to a document:
```javascript
firestore.doc(`/books/id`); // returns a specific document refercence 
```

## Performing CRUD operations in Cloud Firestore
