<template>
    <div>  
        <h6>{{ author }}</h6>
        <p>{{ content }}</p>
        <h5>{{ timestamp }}</h5>
    </div>
</template>

<script>
    export default {
        name: "user-tweets",
        props: {
            author: String,
            content: String,
            timestamp: String
        },
    }
</script>

<style scoped>

</style>