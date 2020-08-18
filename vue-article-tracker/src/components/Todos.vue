<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todos">
           <TodoItem v-bind:todo="todo" 
                     v-on:del-todo="$emit('del-todo',todo.id)" 
                     v-on:status-picked="$emit('status-picked',todo.id)"
                     v-on:status-dispatched="$emit('status-dispatched',todo.id)"
                     v-on:status-received="$emit('status-received',todo.id)"
                     />
        </div>
    </div>
</template>


<script>

import TodoItem from './TodoItem';

export default {
    name: "Todos",
    components: {
        TodoItem
    },
    props: ["todos"]
}
</script>


<style scoped>

</style>