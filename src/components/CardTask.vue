<template>
    <div class="card">
        <p>{{ task.title }}</p>
        <p>{{ task.description }}</p>
        <button @click="deleteCard">×</button>
    </div>
</template>

<script>
export default {
  name: 'Card',
  props: ['task'],
  methods: {
      deleteCard() {
          this.$emit('delete-card', this.task);
      }
  }
}

</script>


<style>
    .card {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        width: 100%;
    }
    .card button {
        background: rgb(255, 75, 111);
        color: #fff;
        border: none;
        border-radius: 4px;
        width: 40px;
        height: 40px;
        font-size: 25px;
        margin-top: 6px;
    }
</style>