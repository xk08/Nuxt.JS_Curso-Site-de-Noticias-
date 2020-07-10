<template>
  <section class="post-list">
    <PostPreview
      id="1"
      :is-admin="isAdmin"
      thumbnail="https://wallpapercave.com/wp/Q9zm0x5.jpg"
      title="Super Mario"
      previewText="O jogo mais irado da galaxia !"
      calendar="07/07/2020"
    />

    <PostPreview
      id="2"
      :is-admin="isAdmin"
      thumbnail="https://images6.alphacoders.com/355/thumb-1920-355348.png"
      title="Minecraft é uma explosão"
      previewText="TTTTTTTTTTTTTTTTTTTSSSSSSSSSSSSSS BOOOOOOOM"
      calendar="07/08/2020"
    />

    <PostPreview
      id="3"
      :is-admin="isAdmin"
      thumbnail="https://mcdn.wallpapersafari.com/medium/32/50/STmIn7.png"
      title="Mortal Kombat, você consegue sobreviver?"
      previewText="Novos combos do Liu-Kang para você"
      calendar="09/07/2020"
    />
  </section>
</template>

<script>
import PostPreview from "@/components/Posts/PostPreview";
export default {
  components: {
    PostPreview
  },
  props: { //Define uma propriedade pro component
    isAdmin: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style scoped>
.post-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>