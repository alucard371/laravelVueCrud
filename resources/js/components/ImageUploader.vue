<template>
    <section id="upload-image-component">
        Upload Images Here:
        <form>
            <input type="file" @change="uploadFile">
            <button>Upload!</button>
        </form>
    </section>
</template>

<script>
    export default {
        name: "ImageUploader",
        methods: {
            uploadFile(event) {
            let file = event.target.files[0];
            let fd = new FormData();
            fd.append('userpic', file);
            for (const value of fd.values()) {
            console.log(value);
            }
            axios.post('/api/uploadimage', fd);
            },
        }
    }
</script>
