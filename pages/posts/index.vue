<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from "@/components/Posts/PostList";
export default {
  components: {
    PostList
  },
  asyncData(context, callback) {
    setTimeout(() => {
      callback(new Error(), {
        loadedPosts: [
          {
            id: "1",
            thumbnail:
              "https://images6.alphacoders.com/355/thumb-1920-355348.png",
            title: "Super Mario",
            previewText: "O jogo mais irado da galaxia !",
            calendar: "13/08/2050"
          },
          {
            id: "2",
            thumbnail: "https://wallpapercave.com/wp/Q9zm0x5.jpg",
            title: "Minecraft é uma explosão",
            previewText: "TTTTTTTTTTTTTTTTTTTSSSSSSSSSSSSSS BOOOOOOOM",
            calendar: "07/08/2020"
          }
        ]
      });
    }, 1500);
  }
};
</script>

<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>