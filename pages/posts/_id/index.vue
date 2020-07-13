<template>
  <div class="single-post-page">
    <section class="post">
      <h1 class="post-title">{{loadedPost.title}}</h1>
      <div class="post-details">
        <div class="post-detail">Last updated on {{loadedPost.updatedDate}}</div>
        <div class="post-detail">Written by {{loadedPost.author}}</div>
      </div>
      <p class="post-content">{{loadedPost.content}}</p>
      <section class="post-feedback">
        <p>Let me know what you think about the post, send a mail to <a href="mailto:gronytzki@gmail.com">mailto:gronytzki@gmail.com</a></p>

      </section>

    </section>

  </div>
</template>

<script>
export default {
  asyncData(context, callback){
    setTimeout(() => {
      callback(null, {
        loadedPost: {
          id: "1",
            title: "Super Mario (ID: " +context.route.params.id +")",
            previewText: "O jogo mais irado da galaxia !",
            author: 'Marcos o XK',
            updatedDate: new Date(),
            content:'Qualquer coisa que desejo exibir',
            thumbnail:
              "https://images6.alphacoders.com/355/thumb-1920-355348.png",
            calendar: "13/08/2050"
        }
      })
    }, 1000)
  }
}
</script>

<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>