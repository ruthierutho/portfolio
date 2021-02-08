<template>
<div>
<section id="project-grid">
  <p></p>
  <project class= "project" v-for="(project, index) in projects" :project="project" :key="index"></project>
</section>
</div>
</template>

<script>
import Project from './project.vue'
export default {
  name: 'my-projects',
  props: ['projects'],
  components: {
    'project': Project
  }

}
</script>

<style>
.project {
    
    background-color: darkseagreen;
    color: lightseagreen;
    font-size: 25pt;
    font-family: 'Montserrat', sans-serif;;
    text-align: center;
    width: 300px;
    height: 350px;
    list-style-type: None;
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
    justify-content: center;
}

.project:hover {
    background-color: seagreen;
    color: darkseagreen;
    cursor: pointer;
}

#project-grid {
    list-style-type: None;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    /* display: grid;
    grid-template-areas: 
      'nothing project project project nothing';
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr; */
    padding: 10px 10px 10px 20px;
    align-content: center;
    align-items: center;
    justify-content: center;
   

   
}


</style>