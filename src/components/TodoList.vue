<template>
    <div>
        <ul>
            <li>
               <TodoItem
                       v-for="(todo, i) of todos"
                       v-bind:todo="todo"
                       v-bind:index="i"
                       v-on:remove-todo="removeTodo"
               />
            </li>
        </ul>
    </div>
</template>

<script>
    import TodoItem from '@/components/TodoItem'
    export default {
        props: ['todos'],
        components: {
            TodoItem: TodoItem
        },
        methods: {
            removeTodo(id){
                this.$emit('remove-todo', id)
            }
        }
    }
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>