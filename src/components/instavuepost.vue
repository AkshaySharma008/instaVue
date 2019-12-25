<template>
    <div class="instavue-post">
        <div class="header level">
            <div class="header-left">
                <figure class="image is-32x32">
                    <img :src="post.userImage" />
                </figure>
                <span class="username">{{post.username}}</span>
            </div>
        </div>
        <div class="image-container"
             :class="post.filter"
             :style="{backgroundImage: 'url(' + post.postImage + ')'}"
             @dblclick="like">
             
    </div>

        <div class="content">
            <div class="heart">
                <i class="far fa-heart fa-lg"
                :class="{'fas':this.post.hasbeenliked}"
                @click="like"></i>
            </div>
            <p class="likes">{{post.likes}}likes</p>
            <p class="caption"><span>{{post.username}}</span>{{post.caption}}</p>
       </div>
    </div>
</template>

<script>
export default{
    name : "instavuepost",
    props:
    {
        post:Object
    },
    methods:{
        like(){
            this.post.hasbeenliked
              ?this.post.likes--
              :this.post.likes++;
        this.post.hasbeenliked = !this.post.hasbeenliked;
        }
    }
};
</script>
<style lang="scss" src="../styles/instavue-post.scss">

</style>