<template>
  <form @submit.prevent="onSave">

    <AppControlInput v-model="editedPost.author">Author Name</AppControlInput>
    <AppControlInput v-model="editedPost.title">Title</AppControlInput>
    <AppControlInput v-model="editedPost.thumbnailLink">Thumbnail Link</AppControlInput>
    <AppControlInput v-model="editedPost.calendar">Calendar</AppControlInput>

    <AppControlInput
      control-type="textarea"
      v-model="editedPost.content"
    >Content</AppControlInput>

    <AppButton type="submit">Save</AppButton>

    <AppButton
      type="button"
      style="margin-left: 10px"
      btn-style="cancel"
      @click="onCancel"
    >Cancel</AppButton>

  </form>
</template>

<script>
import AppControlInput from "@/components/UI/AppControlInput";
import AppButton from "@/components/UI/AppButton";
export default {
  components: {
    AppControlInput,
    AppButton
  },

  props: { //Setando a propriedade pro component
    post: {
      type: Object,
      required: false
    }
  },

  data() {
    return {
        //IF TERNÁRIO
      editedPost: this.post // Condição
        ? { ...this.post } // Se for true (Está editando)
        : { // Se for falso (Está criando um novo)
            author: "",
            title: "",
            thumbnailLink: "",
            calendar: "",
            content: ""
          }
    };
  },
  methods: {
    onSave() {
      console.log(this.editedPost);
    },
    onCancel() {
      this.$router.push("/admin");
    }
  }
};
</script>