<template>
<div class="w-96 mx-auto pt-8">
    <h1 class="ml-12 mb-8">Posts</h1>
    <div>
        <Link :href="route('post.create')" class="hover:bg-white hover:text-sky-500 block p-2 w-32 border border-sky-500 bg-cyan-500 text-center text-white rounded-full">Add Post</Link>
    </div>
</div>
</template>

<script>
import {Link} from "@inertiajs/inertia-vue3";

export default {
    name: "index",
    components: {
        Link
    }
}
</script>

<style scoped>

</style>
