<template>
  <div id="app">
    <md-card>
      <md-card-header>
        <div class="md-title">Material Design With Vue.js Demo</div>      
      </md-card-header>

      <md-card-content>     
        
        <md-table>
          <md-table-header>
            <md-table-row>
              <md-table-head>First name</md-table-head>
              <md-table-head>Last name</md-table-head>
              <md-table-head>Email</md-table-head>
            </md-table-row>
          </md-table-header>
          <md-table-body>
            <md-table-row v-for="contact in contacts" v-bind:key="contact.firstName">
              <md-table-cell>{{ contact.firstName }}</md-table-cell>
              <md-table-cell>{{ contact.lastName }}</md-table-cell>
              <md-table-cell>{{ contact.email }}</md-table-cell>
            </md-table-row>
          </md-table-body>
        </md-table>  


        <sample/>  

      </md-card-content>
    </md-card>
  </div>
</template>

<script>
  
import Sample from './components/Sample.vue'

  export default {
    name: 'app',
    components: {
      
        Sample
    },
    data: function() {
      return {
        contacts: []
      }
    },
    created() {
      this.fillTable()
    },
    methods: {
      fillTable: function() {
        this.contacts.push({firstName: 'Imran', lastName: 'Hossain', email: 'imran@gmail.com'});
        this.contacts.push({firstName: 'Hasan', lastName: 'Ahmed', email: 'hasan@gmail.com'});
        this.contacts.push({firstName: 'Sohan', lastName: 'Rahman', email: 'shohan@gmail.com'});
        console.log(contacts);
      }      
    }
  }
</script>

<style>
  #app {
    margin-top: 60px;
    margin-left: 30px;
    margin-right: 30px;
  }
</style>
