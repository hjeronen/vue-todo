<script>
    let todo = ''

    export default {
        data() {
            return {
                todo: todo
            }
        },
        methods: {
            addTodo() {
                this.$emit('add-todo', this.todo)
                this.todo = ''
            }
        }
    }
</script>

<style scoped>

    .form {
        font-family: Arial, Helvetica, sans-serif;
        width: 600px;
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
        width: 120%
    }

    .text-item.input {
        border-radius: 15px;
        border: 2px solid #526d7a;
        padding: 15px;
        font-size: 16px;
        width: 100%;
    }

    .text-item.input:hover {
        border: 2px solid #8ab9cf;
    }

    .text-item.input:focus {
        border: 2px solid #8ab9cf;
        outline: none;
    }

    .button-item {
        grid-column: 2/2;
        padding: 10px;
        text-align: right;
        margin: auto;
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
    <div class="form">
        <div class="grid-container">
            <div class="text-item">
                <h3 class="h3">Add a thing to do:</h3>
            </div>
            <div class="text-item">
                <input class="text-item input" v-model="todo" placeholder="What to do?" />
            </div>
            <div class="button-item">
                <button class="button" @click="addTodo">Create</button>
            </div>
        </div>
    </div>
</template>
