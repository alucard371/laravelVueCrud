<template>
  <div>
      <masthead :name="name"></masthead>
      <imageuploader></imageuploader>
  </div>
</template>

<script>
import masthead from './masthead';
import imageuploader from './ImageUploader';
export default {


   name: "App",
   components: {
       masthead,
       imageuploader
   },
    data() {
        return {
            name: ''
        }
    },

    mounted() {
        this.index();
    },
    methods: {
        index() {
            axios.get('/api/basicinfo')
            .then(response=>{
                console.log(response.data);
                this.name = response.data.name;
            })
            .catch(error=>{
                console.log(error);
            })
        },

    },

}
</script>

<style scoped>

</style>
