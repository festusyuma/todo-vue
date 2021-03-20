<template>
    <div>
        <form >
            <input type="text" name="title" placeholder="Add Todo.." v-model="title" title="title" >
            <input type="button" value="Submit" class="btn" @click="addTodo" >
        </form>
    </div>
</template>

<script>
import uuid from 'uuid'

export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo() {
            const newTodo = {
                id: uuid(),
                title: this.title,
                completed: false
            }

            this.$emit('add-todo', newTodo)
            this.title = ''
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
}

input[type="text"] {
    flex: 10;
    padding: 5px;
}

input[type='submit'] {
    flex: 2;
}
</style>