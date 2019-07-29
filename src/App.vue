<template>
    <div id="app">
        <div class="container">
            <div class="row">
                <div class="col-sm-12 pt-5">
                    <Todos :todos="todos" @markCompleted="isCompleted" @removeTodo="deleteTodo"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Todos from "./components/Todos"
    export default{
        name: 'app',
        components: {
            Todos,
        },
        methods: {
            isCompleted(id){
                var todo = this.todos.find(todo => todo.id == id)
                todo.completed = !todo.completed
            },
            deleteTodo(id){
                var todoList = this.todos.filter(todo => todo.id !== id)

                this.todos = todoList
            }
        },
        data(){
            return{
                todos: [
                    {
                        "userId": 1,
                        "id": 1,
                        "title": "delectus aut autem",
                        "completed": true
                    },
                    {
                        "userId": 6,
                        "id": 116,
                        "title": "ipsa dolores vel facilis ut",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 143,
                        "title": "eum non recusandae cupiditate animi",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 144,
                        "title": "ut eum exercitationem sint",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 145,
                        "title": "beatae qui ullam incidunt voluptatem non nisi aliquam",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 146,
                        "title": "molestiae suscipit ratione nihil odio libero impedit vero totam",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 147,
                        "title": "eum itaque quod reprehenderit et facilis dolor autem ut",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 148,
                        "title": "esse quas et quo quasi exercitationem",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 149,
                        "title": "animi voluptas quod perferendis est",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 150,
                        "title": "eos amet tempore laudantium fugit a",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 151,
                        "title": "accusamus adipisci dicta qui quo ea explicabo sed vero",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 152,
                        "title": "odit eligendi recusandae doloremque cumque non",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 153,
                        "title": "ea aperiam consequatur qui repellat eos",
                        "completed": false
                    },
                    {
                        "userId": 8,
                        "id": 154,
                        "title": "rerum non ex sapiente",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 155,
                        "title": "voluptatem nobis consequatur et assumenda magnam",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 156,
                        "title": "nam quia quia nulla repellat assumenda quibusdam sit nobis",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 157,
                        "title": "dolorem veniam quisquam deserunt repellendus",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 158,
                        "title": "debitis vitae delectus et harum accusamus aut deleniti a",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 159,
                        "title": "debitis adipisci quibusdam aliquam sed dolore ea praesentium nobis",
                        "completed": true
                    },
                    {
                        "userId": 8,
                        "id": 160,
                        "title": "et praesentium aliquam est",
                        "completed": false
                    },
                    {
                        "userId": 9,
                        "id": 161,
                        "title": "ex hic consequuntur earum omnis alias ut occaecati culpa",
                        "completed": true
                    },
                    {
                        "userId": 9,
                        "id": 162,
                        "title": "omnis laboriosam molestias animi sunt dolore",
                        "completed": true
                    },
                    {
                        "userId": 9,
                        "id": 163,
                        "title": "natus corrupti maxime laudantium et voluptatem laboriosam odit",
                        "completed": false
                    },
                    {
                        "userId": 9,
                        "id": 164,
                        "title": "reprehenderit quos aut aut consequatur est sed",
                        "completed": false
                    }
                ]
            }
        }
    }
</script>
<style>
    @import '~todomvc-common/base.css';
    @import '~todomvc-app-css/index.css';
    .form-control:focus,
    .btn:focus,
    .btn:not(:disabled):not(.disabled):active{
        outline: 0;
        box-shadow: 0 0 0 transparent;
    }
    .footer{
        height: 50px;
    }
</style>