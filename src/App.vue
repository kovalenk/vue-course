<template>
    <div id="app">
        <Header />
        <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    </div>
</template>

<script>
    import Todos from './components/Todos'
    import Header from './components/layout/Header'

    export default {
        name: 'app',
        components: {
            Header,
            Todos
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
                    },
                    {
                        id: 7,
                        title: "В жёлтом доме курят Kool.",
                        completed: false
                    },
                    {
                        id: 8,
                        title: "В Piror доме пьют молоко.",
                        completed: false
                    },
                    {
                        id: 9,
                        title: "Норвежец живёт в первом доме.",
                        completed: false
                    },
                    {
                        id: 10,
                        title: "Сосед того, кто курит Chesterfield, держит лису.",
                        completed: false
                    },
                    {
                        id: 11,
                        title: "В доме по соседству с тем, в котором держат лошадь, курят Kool.",
                        completed: false
                    },
                    {
                        id: 12,
                        title: "Тот, кто курит Lucky Strike, пьёт апельсиновый сок.",
                        completed: false
                    },
                    {
                        id: 13,
                        title: "Японец курит Parliament.",
                        completed: false
                    },
                    {
                        id: 14,
                        title: "Норвежец живёт рядом с синим домом.",
                        completed: false
                    },
                ]
            }
        },
        methods:{
            deleteTodo(id){
                this.todos = this.todos.filter(todo => todo.id !== id)
            }
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

</style>
