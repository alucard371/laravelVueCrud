<template>
    <header>
        <h1>{{ profile.name }}</h1>
        <img v-bind:src="'storage/userpics/' + profile.img_path"/>
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
