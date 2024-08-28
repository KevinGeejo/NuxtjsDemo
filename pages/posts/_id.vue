<template>
    <div>
        <h1>{{ post.title }}</h1>
        <p>{{ post.body }}</p>
        <nuxt-link  to="/posts">Back to posts</nuxt-link>
    </div>
</template>

<script>
export default {
    data() {
        return {
            post: {}
        }
    },
    async fetch() {
        const post = await this.$axios.$get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
        this.post = post
    }
    
}


</script>