<script>

    export default {
        props: {
            todo: {
                type: Object,
                required: true
            }
        },
        methods: {
            toggleDone() {
                this.$emit('toggle-done', this.todo)
            },
            deleteTodo() {
                this.$emit('delete-todo', this.todo)
            }
        }
    }
</script>

<style scoped>
    .todo {
        background-color: #f7f9fa;
        color: black;
        border-radius: 25px;
        border: 2px solid #526d7a;
        width: 100%;
        margin: 10px;
    }

    .todo:hover {
        border: 2px solid #8ab9cf;
    }

    .grid-container {
        display: grid;
        grid-template-columns: 350px auto auto;
        padding: 10px;
        grid-gap: 10px;
        align-items: center;
    }

    .text-item {
        padding: 10px;
        justify-content: left;
    }

    .button-item {
        justify-content: center;
    }

    .delete-button-item {
        justify-content: center;
    }
    
    .done {
        color: grey;
        text-decoration: line-through;
    }

    .button {
        background-color: #008CBA;
        border: none;
        border-radius: 25px;
        color: white;
        padding: 10px 20px;
        text-align: center;
        text-decoration: none;
        font-size: 16px;
        float: right;
    }

    .button.delete {
        background-color: #d13426;
    }

    .button:hover {
        background-color: #029ccf;
        box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
    }

    .button.delete:hover {
        background-color: #f23b29;
    }

    .button:active {
        background-color: #00688a;
        box-shadow: 0 5px #666;
        transform: translateY(4px);
    }

    .button.delete:active {
        background-color: #781f16;
    }
</style>

<template>
    <div class="todo">
        <div class="grid-container">
            <div class="text-item" :class="{ done: todo.done }">
                {{ todo.text }}
            </div>
            <div class="button-item">
                <button class="button" @click="toggleDone">{{ todo.done ? 'Undo' : 'Done' }}</button>
            </div>
            <div class="delete-button-item">
                <button class="button delete" @click="deleteTodo">Delete</button>
            </div>
        </div>
    </div>
</template>
