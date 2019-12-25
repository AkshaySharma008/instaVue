<template>
 <div class="phone-body">
     <div class="feed">
          <instavue-post v-for="post in posts"
          :post="post"
          :key="posts.indexOf(post)">
          </instavue-post>
     </div>
  </div>
</template>

<script>
import instavuepost from "./instavuepost";

export default {
    name :"phonebody",
    props:{
        posts:Array,
        filters:Array
    },
    components:{
        "instavue-post":instavuepost
    }
};
</script>

<style lang="scss" src="../styles/phone-body.scss">
</style>    