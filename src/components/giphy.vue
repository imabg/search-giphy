<template>
    <div v-if="giphy_send">
        <img :src = giphy_url alt="Gif's">
    </div>
</template>

<script>
export default {
    name: 'giphy',
    props: {
        giphy_url: {
            type: String,
            required: true
        },
        giphy_send: {
            type: Boolean,
            required: true
        }
    }
}
</script>

<style scoped>
    img {
        height: 400px;
        width: 400px;
    }
</style>

