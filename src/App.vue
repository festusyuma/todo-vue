<template>
    <div id="app">
        <h1>Todos</h1>
        <Todos :todos=todos @del-todo="deleteTodo" />
    </div>
</template>

<script>

import Todos from './components/Todos'

export default {
    name: 'App',
    components: {
        Todos
    },
    data() {
        return {
            todos: [
                {
                    id: 1,
                    title: 'one',
                    completed: false
                },
                {
                    id: 2,
                    title: 'two',
                    completed: true
                },
                {
                    id: 3,
                    title: 'three',
                    completed: false
                }
            ]
        }
    },
    methods: {
        deleteTodo(id) {
            this.todos = this.todos.filter(todo => todo.id !== id)
        }
    }
}
</script>

<style>
*{
    padding: 0;
    margin: 0;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
}
</style>
