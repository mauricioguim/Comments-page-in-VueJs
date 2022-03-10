<template>
  <div class="container">
    <h1>Comentários</h1>
    <hr>
    <div class="col-md-12">
      <form action="" method="post">
        <FormTodo v-on:add-comment="addComment"></FormTodo>
      </form>
    </div>
    <div class="list-group">
      <p v-if="comments.length <= 0">Ainda não há comentários</p>
      <small class="list-group-item" v-for="comment in comments" :key="comment">
        <h4 class="list-group-item-heading">{{ comment.name }}</h4>
        <p class="list-group-item-text">{{ comment.message }}</p>
        <div>
          <button type="submit" href="#" class="btn btn-danger" v-on:click="deleteComment">Excluir</button>
        </div>
      </small>
    </div>
    <hr>
  </div>
</template>

<script>
  import FormTodo from "./FormTodo.vue";

  export default {
    name: 'Comment-list',
    components: {
      FormTodo
    },
    data() {
      return {
        comments: []
      }
    },
    methods: {
      addComment(comment) {
        this.comments.push(comment);
      },
      deleteComment(index) {
        this.comments.splice(index, 1);
      }
    }
  }
</script>

<style scoped>

</style>
