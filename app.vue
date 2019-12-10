<template>
 <div>
    <table>
        <tbody>
            <tr v-for="todo in todos" :key="todo.id" >
               <img v-bind:src="todo.thumbnailUrl"/>
               <td>{{ todo.title }}</td>  
            </tr>
        </tbody>
    </table>
 </div> 
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return {
           todos : null 
        }
    },
    mounted(){
        this.getTodos();
    },
    methods: {
        getTodos(){
            axios
            .get('https://jsonplaceholder.typicode.com/photos')
               .then( response => {
                   this.todos = response.data
               })
               .catch( e=> console.log(e))
        }

    }
}
</script>

<style>

</style>