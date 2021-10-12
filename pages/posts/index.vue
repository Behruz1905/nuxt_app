<template>
    <div>
           <div>

        <h2>Making API request - the vue way</h2>
    </div>
   
    <div class="container">
        <Card v-for="post in posts" :key="post.id" :post="post"/>
        <button class="btn btn-danger" v-scroll-to="'body'">Back to Top</button>
    </div>
    </div>
</template>




<script>

import axios from 'axios';
import Card from '@/components/Card'
import {mapGetters} from 'vuex'

export default {
    components: {
        Card
    },
    data() {
        return {
            allPosts: []
        }
    },
    computed: {
        // allPosts() {
        //     return this.$store.getters.posts;
        // }
        ...mapGetters(['posts'])
    },
    async fetch({ store }){

        let {data} =  await axios.get("https://jsonplaceholder.typicode.com/posts");

        // return {posts: data}

        store.dispatch('setPosts', data)
               
        
    },
    head: {
        title : "List of the posts"
    }
}






// import axios from 'axios';
// export default {
//     data() {
//         return {
//             posts: []
//         }
//     },

//     mounted (){
//         axios.get("https://jsonplaceholder.typicode.com/posts")
//                 .then(response => {
//                     console.log(response)
//                     this.posts = response.data
//                 }).catch((error) => {
//                         console.log(error)
//                 })
//     }
// }
</script>