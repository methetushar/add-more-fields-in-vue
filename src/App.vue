<template>
  <div id="app">
    <b-navbar toggleable="lg" type="light" variant="light">
      <b-container>
        <b-navbar-brand href="#">NavBar</b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="#">Home</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ms-auto">
            <b-nav-item-dropdown text="Lang" right>
              <b-dropdown-item href="#">EN</b-dropdown-item>
              <b-dropdown-item href="#">ES</b-dropdown-item>
              <b-dropdown-item href="#">RU</b-dropdown-item>
              <b-dropdown-item href="#">FA</b-dropdown-item>
            </b-nav-item-dropdown>

            <b-nav-item-dropdown right>
              <!-- Using 'button-content' slot -->
              <template #button-content>
                <em>User</em>
              </template>
              <b-dropdown-item href="#">Profile</b-dropdown-item>
              <b-dropdown-item href="#">Sign Out</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
    <b-container class="mt-5">
      <b-card class="shadow-sm border-0">
        <h2 class="text-success"><b-icon-list-check></b-icon-list-check> Data Collection</h2>
        <b-card-body>
          <Form :formData="data" @addmore="addNewData" @remove="removeField" />
        </b-card-body>
      </b-card>
    </b-container>

  </div>
</template>

<script>

import Form from "./components/Form";
export default {
  name: 'App',
  components: {Form},
  data(){
    return{
      data:[
        {
          name:'',
          phone:'',
          address:''
        }
      ]
    }
  },
  methods:{
    addNewData(){
      this.data.push({
        name:'',
        phone:'',
        address:''
      })
    },
    removeField(index){
      this.data.splice(index,1)
    }
  }
}
</script>

