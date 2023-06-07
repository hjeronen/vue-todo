<script>
    import TodoItem from './TodoItem.vue'
    export default {
        components: {
            TodoItem
        }
    }
</script>

<style scoped>
    .list {
        width: 600px;
    }
</style>

<template>
    <div class='list'>
        <TodoItem />
    </div>
</template>
