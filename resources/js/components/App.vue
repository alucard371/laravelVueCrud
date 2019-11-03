<template>
  <div>
      <masthead :name="name"></masthead>
      <img v-bind:src="'storage/userpics/' + imagepath"/>
      <!-- Debug imagepath -->
      <!-- {{ imagepath }} -->
      <!-- <imageuploader></imageuploader> -->
  </div>
</template>

<script>
import masthead from './masthead';
// import imageuploader from './ImageUploader';
import ProfileEditor from './ProfileEditor';
export default {


   name: "App",
   components: {
       masthead,
    //    imageuploader
   },
    data() {
        return {
            name: '',
            imagepath: '',
        }
    },

    mounted() {
        this.index();
        this.getImagePath();
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
        getImagePath() {
            axios.get('/api/image')
        .then(response => {
            this.imagepath = response.data.path;
        })
        .catch(error => {
            console.log(error);
        });
        },
    },
}
</script>

<style scoped>

</style>
