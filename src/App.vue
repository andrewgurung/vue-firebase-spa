<template>
  <div id="app">
  </div>
</template>

<script>
import Hello from './components/Hello'

import Firebase from 'firebase '

let config = {
  apiKey: "AIzaSyBBOM9pZwE_KdRVCbZjLANWAv-E-5cpB7g",
  authDomain: "vue-firebase-spa.firebaseapp.com",
  databaseURL: "https://vue-firebase-spa.firebaseio.com",
  projectId: "vue-firebase-spa",
  storageBucket: "vue-firebase-spa.appspot.com",
  messagingSenderId: "529425484072"
}

let app = Firebase.initializeApp(config);
let db = app.datebase();

let booksRef = db.ref('books');

export default {
  name: 'app',
  firebase: {
    books: booksRef
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
