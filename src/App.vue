<template>
  <div id="app" class="container">
    <div class="page-header">
      <h1>Vue.js 2 & Firebase Sample Application</h1>
    </div>
    <div class="panel panel-default">
      <div class="panel-heading">
        <h3>Book Lists</h3>
      </div>
      <div class="panel-body">
        <table class="table table-striped">
          <thead>
            <tr>
              <th>
                Title
              </th>
              <th>
                Author
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="book in books">
              <td>
                <a v-bind:href="book.url">{{book.title}}</a>
              </td>
              <td>
                {{book.author}}
              </td>
            </tr>
          </tbody>

        </table>
      </div>
    </div>
  </div>
</template>

<script>
import Hello from './components/Hello'

import Firebase from 'firebase'

let config = {
  apiKey: "AIzaSyBBOM9pZwE_KdRVCbZjLANWAv-E-5cpB7g",
  authDomain: "vue-firebase-spa.firebaseapp.com",
  databaseURL: "https://vue-firebase-spa.firebaseio.com",
  projectId: "vue-firebase-spa",
  storageBucket: "vue-firebase-spa.appspot.com",
  messagingSenderId: "529425484072"
}

let app = Firebase.initializeApp(config);
let db = app.database();

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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
