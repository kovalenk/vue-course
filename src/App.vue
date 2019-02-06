<template>
    <div id="app">
        <Header/>
        <AddTodo v-on:add-todo="addTodo"/>
        <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    </div>
</template>

<script>
    import Todos from './components/Todos'
    import AddTodo from './components/AddTodo'
    import Header from './components/layout/Header'

    export default {
        name: 'app',
        components: {
            Header,
            Todos,
            AddTodo
        },
        data() {
            return {
                todos: [
                    {
                        id: 1,
                        title: "Англичанин живёт в красном доме",
                        completed: false
                    },
                    {
                        id: 2,
                        title: "У испанца есть собака.",
                        completed: false
                    },
                    {
                        id: 3,
                        title: "В зелёном доме пьют кофе.",
                        completed: false
                    },
                    {
                        id: 4,
                        title: "Украинец пьёт чай.",
                        completed: false
                    },
                    {
                        id: 5,
                        title: "Зелёный дом стоит сразу справа от белого дома.",
                        completed: false
                    },
                    {
                        id: 6,
                        title: "Тот, кто курит Old Gold, разводит улиток.",
                        completed: false
                    }
                ]
            }
        },
        methods: {
            deleteTodo(id) {
                this.todos = this.todos.filter(todo => todo.id !== id)
            },
            addTodo(newTodo){
                this.todos = [...this.todos, newTodo];
            },
        }
    }
</script>

<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body {
        font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
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

    .btn:hover{
        background: #666;
    }
</style>
