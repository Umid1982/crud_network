<template>

    <h1 class="ml-12 mb-8">Posts</h1>
    <div class="mb-8">
        <Link :href="route('post.create')" class="hover:bg-white hover:text-sky-500 block p-2 w-32 border border-sky-500 bg-cyan-500 text-center text-white rounded-full">Add Post</Link>
    </div>
    <div v-if="posts">
        <div class="mt-8 pt-8 border-t border-gray-300" v-for="post in posts">
            <div>Id: {{post.id}}</div>
            <div>Title: {{post.title}}</div>
            <div>Content: {{post.content}}</div>
            <div class="text-sm text-right">{{post.date}}</div>
            <div class="text-sm text-right">
                <Link class="text-sky-500" :href="route('post.show',post.id)">Show</Link>
            </div>
            <div class="text-sm text-right">
                <Link class="text-sky-500" :href="route('post.edit',post.id)">Edit</Link>
            </div>
            <div class="text-sm text-right">
                <p @click="deletePost(post.id)" class="cursor-pointer text-red-500">Delete</p>
            </div>
        </div>
    </div>

</template>

<script>
import {Link} from "@inertiajs/inertia-vue3";
import MainLayout from "@/Layouts/MainLayout.vue";

export default {
    name: "index",
    layout: MainLayout,
    props:[
        'posts',
    ],
    components: {
        Link
    },
    methods: {
        deletePost(id)
        {
            this.$inertia.delete(`/posts/${id}`)
        }    }

}
</script>

<style scoped>

</style>
