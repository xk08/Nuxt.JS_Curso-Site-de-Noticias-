<template>
  <div class="admin-page">
    <section class="new-post">
      <AppButton @click="$router.push('/admin/new-post')">Create Post</AppButton>
    </section>
    <section class="existing-posts">
      <h1>Existing Posts</h1>
      <PostList
        isAdmin
        :posts="loadedPosts"
      />
    </section>
  </div>
</template>

<script>
import PostList from "@/components/Posts/PostList";
import AppButton from "@/components/UI/AppButton";

export default {
  layout: "admin",
  components: {
    PostList,
    AppButton
  },
  asyncData(context, callback) {
    setTimeout(() => {
      callback(null, {
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
.admin-page {
  padding: 20px;
}

.new-post {
  text-align: center;
  border-bottom: 2px solid #ccc;
  padding-bottom: 10px;
}

.existing-posts h1 {
  text-align: center;
}
</style>