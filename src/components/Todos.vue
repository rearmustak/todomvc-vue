<template>
    <div>
        <section class="todoapp">
            <header class="header">
                <h1>todos</h1>
                <input class="new-todo" placeholder="What needs to be done?" autofocus>
            </header>
            <section class="main">
                <input id="toggle-all" class="toggle-all" type="checkbox">
                <label for="toggle-all">Mark all as complete</label>
                <ul class="todo-list">
                    <li :key="todo.id" v-for="todo in todos" :class="{'completed':todo.completed}">
                        <div class="view">
                            <input class="toggle" type="checkbox" :checked="todo.completed" @change="markCompleted(todo.id)">
                            <label>{{todo.title}}</label>
                            <button class="destroy" v-if="todo.completed" @click="removeTodo(todo.id)"></button>
                        </div>
                        <input class="edit" value="Create a TodoMVC template" />
                    </li>
                </ul>
            </section>
            <footer class="footer">
                <span class="todo-count"><strong>0</strong> item left</span>
                <ul class="filters">
                    <li>
                        <a class="selected" href="#/">All</a>
                    </li>
                    <li>
                        <a href="#/active">Active</a>
                    </li>
                    <li>
                        <a href="#/completed">Completed</a>
                    </li>
                </ul>
                <button class="clear-completed">Clear completed</button>
            </footer>
        </section>
        <footer class="info">
            <p>Double-click to edit a todo</p>
            <p>Template by <a href="http://sindresorhus.com">Sindre Sorhus</a></p>
            <p>Created by <a href="http://todomvc.com">you</a></p>
            <p>Part of <a href="http://todomvc.com">TodoMVC</a></p>
        </footer>
    </div>
</template>

<script>
    export default{
        name: "Todos",
        props: ['todos'],
        methods: {
            markCompleted(id){
                this.$emit("markCompleted", id)
            },
            removeTodo(id){
                this.$emit('removeTodo', id)
            }
        },
    }
</script>
