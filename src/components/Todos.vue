<template>
    <div>
        <h1>Todos</h1>
        {{todos}}
    </div>
</template>

<script>
export default {
    name: "Todos",
    props: {
        todos: Array
    }
}
</script>

<style scoped>

</style>
