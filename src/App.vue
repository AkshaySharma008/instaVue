<template>
  <div id="app">
    <div class="app-phone">
      <div class="phone-header">
        <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/1211695/vue_gram_logo_cp.png" />
      </div>
      <phone-body
         :step="step"  
        :posts="posts"
        :filters="filters"
        :image="image"
        :selectedfilter="selectedfilter"
        v-model="caption"/>

      <div class="phone-footer">
       <div class="home-cta">
        <i class="fas fa-home fa-lg"></i>
       </div>
       <div class="upload-cta">
         <input type="file"
           name="file"
           id="file"
           class="inputfile"
           @change="uploadImage"/>
           <label for="file">
        <i class="far fa-plus-square fa-lg"></i>
           </label>
       </div>
      </div>
    </div>
  </div>
</template>

 <script>
 import phonebody from "./components/phonebody";
 import posts from "./data/posts";
 import filters from "./data/filters";
  
  export default{
      name: "app",
      methods:{
        uploadImage(evt){
          const files = evt.target.files;
          if(!files.length) return;

          const reader =new FileReader();
          reader.readAsDataURL(files[0]);
          reader.onload = evt =>{
            this.image = evt.target.result;
            this.step=2;
          };
          document.querySelector("#file").value="";

        }
      },
      data(){
        return {
          step:1,
          posts,
          filters,
          image: "",
          selectedfilter: "",
          caption: "",
        };
      },
      components:{
          "phone-body" : phonebody
      }
  };
  </script>

  <style lang="scss" src="./styles/app.scss">
        
  </style>



