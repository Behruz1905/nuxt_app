<template>
    <div>
        <div class="card" style="width: 100%; margin-bottom: 4px;">
            <div class="card-body">
                <h5 class="card-title">{{post.title}}</h5>
                <p class="card-text">{{post.body}}</p>
                <nuxt-link class="card-link" :to="{name: 'posts-id', params: {id: post.id}}">Look post</nuxt-link>
              
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:  {
        post: Object
    }
}
</script>