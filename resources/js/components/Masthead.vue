<template>
    <header>
        <img v-bind:src="'storage/userpics/' + profile.img_path"/>
        <h1>{{ profile.name }}</h1>
    </header>
</template>

<script>
export default {
    name: "masthead",
    props: {
        // name: String
        profile: Object
    },
    data() {
        return {
            profile: Object
        }
    }
}
</script>

<style scoped>
header{
    background: #04BC92;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    height: 100vh;
}
</style>
