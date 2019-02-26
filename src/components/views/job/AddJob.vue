<template>
  <div class="container">
        <div class="card">
            <div class="card-header">
                <h3>Add Job</h3>
            </div>
            <div class="card-body">
                <form v-on:submit.prevent="addJob">
                    <div class="form-group">
                        <label>Job Title:</label>
                        <input type="text" class="form-control" v-model="newJob.title"/>
                    </div>
                    <div class="form-group">
                        <label>Job Task:</label>
                        <input type="text" class="form-control" v-model="newJob.author"/>
                    </div>
                    <div class="form-group">
                        <input type="submit" class="btn btn-primary" value="Add Job"/>
                    </div>
                </form>
            </div>
        </div>
        <div>
    <h1>List Item</h1>
    <table class="table table-striped">
      <thead>
        <tr>
          <th>Item Name</th>
          <th>Item Price</th>
          <th colspan="2">Action</th>
        </tr>
      </thead>
      <tbody>
          <tr v-for="job of jobs">
            <td><a v-bind:href="job.url">{{job.title}}</a></td>
            <td>{{job.author}}</td>
            <td>{{job.url}}</td>
           <!-- <td>
                <router-link :to="{ name: 'Edit', params: {id: item['.key']} }" class="btn btn-warning">
                  Edit
                </router-link>
            </td>
            <td>
              <button @click="deleteItem(item['.key'])" class="btn btn-danger">Delete</button>
            </td>
            <td><span class="glyphicon glyphicon-trash" aria-hidden="true" v-on:click="removeBook(book)"></span></td>
          -->
          </tr>
      </tbody>
    </table>
  </div>

    </div>
</template>
<script>
import { firebase } from '../../../FirebaseAuthPlugin'
import FirebaseAuthPlugin from '../../../FirebaseAuthPlugin'
let db = firebase.database()
let booksRef = db.ref('books')
export default {
  components: {
      name: 'AddJob'
  },
  firebase: {
    jobs: db.ref('books')
  },
  data () {
    return {
      newJob: {
          title: '',
          task: ''
      }
    }
  },
  methods: {
      addJob: function () {
        booksRef.push(this.newJob);
        this.newJob.title = '';
        this.newJob.author = '';
        //this.newJob.url = 'http://';
      },
      removeBook: function (book) {
        booksRef.child(book['.key']).remove()
        toastr.success('Book removed successfully')
      }
    }
}
</script>