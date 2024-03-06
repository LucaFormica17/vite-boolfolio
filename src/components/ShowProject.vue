<script>
import { store } from '../store.js';
import axios from 'axios';
export default {
  name: 'ShowProject',
  data() {
    return {
      store,
      project: null,
    }
  },
  created(){

    this.getProject();
    
  },
  methods: {
    getProject(){

      axios.get(`http://127.0.0.1:8000/api/project/${this.$route.params.id}`).then((response) =>{

        if(response.data.success){

            this.project = response.data.response;
        }
        else{
          this.$router.push({ name: 'not-found' });
        }
      });
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="btn btn-sm btn-primary" @click="console.log(this.project)">Check!</div>
    <h1>{{ this.project[1].title }}</h1>
  </div>
</template>

<style scoped>
</style>