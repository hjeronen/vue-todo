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
                this.$emit('toggle-done', this.todo);
            }
        }
    }
</script>

<style>
    .todo {
        background-color: #f7f9fa;
        color: black;
        border-radius: 25px;
        border: 2px solid #526d7a;
        width: 90%;
    }

    .todo:hover {
        border: 2px solid #8ab9cf;
    }

    .grid-container {
        display: grid;
        grid-template-columns: auto auto;
        padding: 10px;
        grid-gap: 10px;
        align-items: center;
    }

    .text-item {
        grid-column: 1/2;
        padding: 10px;
        justify-content: left;
    }

    .button-item {
        grid-column: 2/2;
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
        padding: 15px 32px;
        text-align: center;
        text-decoration: none;
        font-size: 16px;
        float: right;
    }

    .button:hover {
        background-color: #029ccf;
        box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
    }

    .button:active {
        background-color: #00688a;
        box-shadow: 0 5px #666;
        transform: translateY(4px);
    }
</style>

<template>
    <div class="todo">
        <div class="grid-container">
            <div class="text-item" :class="{ done: todo.done }">
                {{ todo.text }}
            </div>
            <div class="button-item">
                <button class="button" @click="toggleDone">{{ todo.done ? 'Undo' : 'Mark Done' }}</button>
            </div>
        </div>
    </div>
</template>
