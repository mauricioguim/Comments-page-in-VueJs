<template>
  <div class="form-todo form-group">
    <label for="name">Nome</label>
    <input type="text" name="name" class="form-control" id="name" placeholder="Nome" v-model="name">
  </div>
  <div class="form-group">
    <label for="comment">Comentário</label>
    <textarea name="comment" class="form-control" id="comment" rows="3" v-model="message"></textarea>
  </div>
  <button type="button" class="btn btn-primary" style="margin: 10px" v-on:click="addComment">Enviar</button>
</template>

<script>
  export default {
    name: "FormTodo",
    data: function() {
      return {
        name: "",
        message: ""
      };
    },

    methods: {
      addComment: function () {
        this.$emit("add-comment", {
          name: this.name,
          message: this.message
        });
        this.name = "";
        this.message = "";
      }
    }
  }
</script>

<style scoped>

</style>
