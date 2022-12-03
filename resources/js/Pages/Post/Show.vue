<template>

    <h1 class="ml-12 mb-8">Post</h1>
    <div class="ml-2 mb-2">
        <Link :href="route('post.index')" class="text-sky-500 text-sm mb-8">Back</Link>
    </div>
    <div v-if="post">
        <div class="mt-8 pt-8 border-t border-gray-300">
            <div>Id: {{post.id}}</div>
            <div>Title: {{post.title}}</div>
            <div>Content: {{post.content}}</div>
            <div class="text-sm text-right">{{post.date}}</div>
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
        'post',
    ],
    components: {
        Link
    }
}
</script>

<style scoped>

</style>
