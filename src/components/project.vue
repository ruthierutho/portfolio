<template>
<ul>
    <li v-on:click="handleClick">
        <div v-if = "project.name === 'Fruits of the World: Group Javascript/Vue Project' " >
       <img class="icon" src="../images/bananas.png" alt="bananas" width=100px>
       </div>
       <div v-else-if = "project.name === 'Disneyland Bucket List: Solo Python Project'">
           <img class="icon" src="../images/disneyland.png" alt="disneyland" width=100px>
       </div>
        <div v-else-if = "project.name === 'RoundIn Ordering: Group Java/React Project'">
           <img class="icon" src="../images/beer.png" alt="beer pint" width=100px>
       </div>
       <div v-else-if = "project.name === 'Music Box: Post-CodeClan Solo React App'">
           <img class="icon" src="../images/saxophone.png" alt="saxophone" width=120px>
       </div>

      <p class="project-name">{{project.name}}</p>
    </li>
</ul>
</template>

<script>
import { eventBus } from '../main'
export default {
    name: 'project',
    props: ['project'],
    methods: {
        handleClick(){
            eventBus.$emit('project-selected', this.project)
        }
    }
}
</script>

<style>
.project-name {
    margin:25px 0px;
}

.icon {
    margin: 15px 0px 0px 0px;
}
</style>