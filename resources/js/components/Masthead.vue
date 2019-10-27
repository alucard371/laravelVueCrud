<template>
    <header>
        <h1>{{ name }}</h1>
    </header>
</template>

<script>
export default {
    name: "masthead",
    props: {
        name: String
    }
}
</script>
