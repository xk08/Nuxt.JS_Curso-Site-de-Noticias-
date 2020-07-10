<template>
  <div class="admn-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost" />
    </section>
  </div>
</template>

<script>
import AdminPostForm from "@/components/Admin/AdminPostForm";
export default {
  layout: "admin",
  components: {
    AdminPostForm
  },
  data() {
    return {
      loadedPost: {
        author: "Marcos do plural",
        title: "Este post é incrível",
        content: "Olha só como esse post é top da galaxya",
        calendar: "10/07/2020",
        thumbnailLink: "https://wallpapercave.com/wp/Q9zm0x5.jpg"
      }
    };
  }
};
</script>

<style scoped>
.update-form {
  width: 90%;
  margin: 20px auto;
}

@media (min-width: 768px) {
  .update-form {
    width: 500px;
  }
}
</style>