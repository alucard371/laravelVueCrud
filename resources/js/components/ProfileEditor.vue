<template>
  <form action="">
      <input type="text" v-model="name" name="" id="">
      <input type="file" name="" id="" accept="image/*" @change="selectFile">
      <button @click.prevent="onSubmit">Submit</button>
  </form>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            file: null,
        }
    },
    methods: {
        selectFile(event) {
            this.file = event.target.files[0];
        },
        onSubmit() {
            let fd = new FormData();
            fd.append('name', this.name);
            fd.append('userpic', this.file);

            for (let x of fd.values()) {
            console.log(x);
            }

            axios.post('api/profile', fd).then(response => console.log(response));
        },
    }
}
</script>

<style>

</style>
