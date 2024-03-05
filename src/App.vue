<script>
import axios from 'axios';

export default {
  components:{
    
  },
  data(){
    return{
      projects: [],
    }
  },
  created(){
    this.getProjects();
  },
  methods: {
    getProjects(){
      axios.get('http://127.0.0.1:8000/api/projects').then((response) => {
        this.projects = response.data.results;
        console.log(this.projects);
      })
    }
  }
}
</script>
<template lang="">
  <div>
    
  </div>
</template>
<style lang="">
  
</style>