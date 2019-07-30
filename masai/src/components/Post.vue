<template>
    <div class="blog-post">
        <h3>{{ posted.title }}</h3>
        <div v-html="posted.content"></div>
    </div>
</template>
<script>
export default {
    name : 'Post',
    props : ['posted']//定一个自定义props
}
</script>

