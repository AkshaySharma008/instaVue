<template>
  <div id="app">
    <div class="app-phone">
      <div class="phone-header">
        <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/1211695/vue_gram_logo_cp.png" />
      </div>
      <phone-body  
        :posts="posts"
        :filters="filters"/>
        
      <div class="phone-footer">
       <div class="home-cta">
        <i class="fas fa-home fa-lg"></i>
       </div>
       <div class="upload-cta">
        <i class="far fa-plus-square fa-lg"></i>
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
      data(){
        return {
          posts,
          filters,
        };
      },
      components:{
          "phone-body" : phonebody
      }
  };
  </script>

  <style lang="scss" src="./styles/app.scss">
        
  </style>



