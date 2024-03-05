<script>
import ProjectCard from './ProjectCard.vue';
import axios from 'axios';

export default {
  name: 'AppMain',
  components: {
    ProjectCard,
  },
  data(){
    return {
      projects: [],
    }
  },
  created(){
    this.getProjects();
  },
  methods: {
    getProjects(){
      axios.get(`http://127.0.0.1:8000/api/projects`).then((response) =>{
        this.projects = response.data.results;

      });
    }
  }
}
</script>

<template>
  <div class="container">
    <h1 class="text-center">Boolfolio</h1>
    <div class="row">
      <ProjectCard v-for="project, index in this.projects" :key="index" :project="project" />
    </div>
  </div>
</template>

<style scoped>
</style>
