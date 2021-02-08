<template>
<ul>
    <li v-on:click="handleClick">
        <div v-if = "project.name === 'Group Javascript/Vue Project: Fruits of the World' " >
       <img src="../images/bananas.png" alt="bananas" width=100px>
       </div>
       <div v-else-if = "project.name === 'Solo Python Project: Disneyland ToDo List'">
           <img src="../images/disneyland.png" alt="disneyland" width=100px>
       </div>
        <div v-else-if = "project.name === 'Group Java/React Project: RoundIn Ordering App'">
           <img src="../images/beer.png" alt="beer pint" width=100px>
       </div>

      <p>{{project.name}}</p>
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

</style>