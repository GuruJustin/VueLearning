<template>
    <div class = "container">
        <table class="table mt-4">
            <thead>
                <tr>
                <th scope="col">userId</th>
                <th scope="col">Id</th>
                <th scope="col">Title</th>
                <th scope="col">Completed</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="post in posts" :key ="post.id" >
                    <td>{{post.id}}</td>
                    <td>{{post.title}}</td>
                    <td>{{post.completed}}</td>
                </tr>
            </tbody>
            </table>
    </div>
</template>
<script>
import axios from 'axios';

export default {
    name : 'PostsExample',
    props : [
        'posts'
    ],
    data() {
        return {

        }
    },
    created() {

        axios.get('https://jsonplaceholder.typicode.com/todos').then( posts =>{
            this.posts = posts.data;
        })
    }
}
</script>