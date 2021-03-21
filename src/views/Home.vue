<template>
    <div id="app">
        <AddTodo @add-todo="addTodo" />
        <Todos :todos=todos @del-todo="deleteTodo" />
    </div>
</template>

<script>

import Todos from "@/components/Todos";
import AddTodo from "@/components/AddTodo";
import axios from 'axios'

export default {
    name: 'Home',
    components: {
        Todos,
        AddTodo
    },
    data() {
        return {
            todos: []
        }
    },
    created() {
        axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
            .then(response => this.todos = response.data)
            .catch(error => console.log(error))
    },
    methods: {
        deleteTodo(id) {
            axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
                .then(() => this.todos = this.todos.filter(todo => todo.id !== id))
                .catch(error => console.log(error))
        },

        addTodo(todo) {
            const {title, completed} = todo

            axios.post('https://jsonplaceholder.typicode.com/todos', {title, completed})
                .then(res => this.todos.push(res.data))
                .catch(error => console.log(error))
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

.btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
}

.btn:hover {
    background: #666;
}
</style>
