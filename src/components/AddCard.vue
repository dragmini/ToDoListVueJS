<template>
  <div class="add-block">
    <input id="inputTitle" placeholder="Title">
    <textarea id="inputDescription" class="description" placeholder="Description"></textarea>
    <button v-on:click="saveCard" id="my-div" class="btn-save">Save</button>
  </div>
</template>

<script>
  export default {
    methods: {
        saveCard: function() {
          let inputTitle = document.getElementById('inputTitle').value
          let inputDescription = document.getElementById('inputDescription').value

          this.$emit('save-data-card', {
            title: inputTitle, 
            description: inputDescription
          });
          console.log(1)
        }
    }
  }
</script>

<style>
  .add-block {
    background: #fff;
    display: flex;
    flex-direction: column;
    padding: 10px;
  }
  .add-block input, textarea, button{
    margin: 5px;
    height: 30px;
  }
  .description {
    height: 100px;
    resize: none;
  }
  .btn-save {
    background: rgb(69, 163, 81);
    border: none;
    border-radius: 4px;
    color: rgb(255, 255, 255);
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-size: 20px;
    font-weight: bold;
  }
</style>
