<template>
  <div>
      <masthead :profile="profile"></masthead>
      <!-- <img v-bind:src="'storage/userpics/' + profile.img_path"/> -->
      <!-- Debug imagepath -->
      <!-- {{ imagepath }} -->
      <!-- <imageuploader></imageuploader> -->
      <ProfileEditor></ProfileEditor>
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
    ProfileEditor,
   },
    data() {
        return {
            name: '',
            imagepath: '',
            profile: '',
        }
    },

    mounted() {
        // this.index();
        // this.getImagePath();
        this.getProfile();
    },
    methods: {
        // index() {
        //     axios.get('/api/basicinfo')
        //     .then(response=>{
        //         console.log(response.data);
        //         this.name = response.data.name;
        //     })
        //     .catch(error=>{
        //         console.log(error);
        //     })
        // },
        // getImagePath() {
        //     axios.get('/api/image')
        // .then(response => {
        //     this.imagepath = response.data.path;
        // })
        // .catch(error => {
        //     console.log(error);
        // });
        // },
        getProfile() {
            axios.get('/api/profile')
            .then(response => {
                console.log(response.data);
                this.profile = response.data;
            })
            .catch(error => {
                console.error(error);
            });
        }
    },
}
</script>

<style scoped>
body{
    margin: 0;
}
</style>
