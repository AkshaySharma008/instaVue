<template>
    <div class="instavue-post">
        Hello
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
             :style="{backgroundImage: 'url(' + post.postImage + ')'}">
             
    </div>

        <div class="content">
            <div class="heart">
                <i class="far fa-heart fa-lg"></i>
            </div>
            <p class="likes">{{posts.likes}}likes</p>
            <p class="caption"><span>{{post.username}}</span>{{span.caption}}</p>
       </div>
    </div>
</template>

<script>
export default{
    name : "instavuepost",
    props:
    {
        post:Object
    }
};
</script>
<style lang="scss" src="../styles/instavue-post.scss">

</style>