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
```javascript
firestore.collection('books'); // returns a collection reference called books
```
- Connect to a document:
```javascript
firestore.doc(`/books/id`); // returns a specific document refercence 
```

## Performing CRUD operations in Cloud Firestore
- Create (add) a new document with auto-generated ID
```javascript
firestore.collection('books').add(data); // returns a promise
  // Alternatively
  firestore.collection('books').set(data);
```
- Get (read) all documents from a collection:
```javascript
import { collectionData } from 'rxfire/firestore';
  const bookCollectionRef = firestore.collection('books');
  collectionData(booksCollectionRef, 'id'); // returns an observable
```
- Get a single document from a collection:
```javascript
import {docData} from 'rxfire/firestore';
  
  const bookRef = firestore.doc(`/books/id`);
  docData(bookRef, 'id'); // returns an observable
```
- Update a specific document in a collection:
```javascript
firestore.doc(`/books/id`).update(data);  // returns a promise
  
  // Alternatively
  firestore.collection('books').doc('id').update(data, {merge: true})
```
- Delete a specific document in a collection:
```javascript
firestore.doc(`/books/id`).delete(); // returns a promise
```
