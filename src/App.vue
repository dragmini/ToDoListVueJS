<template>
  <div id="app">
    <h3>ToDoList</h3>
    <div id="body-block">
      <AddCard @save-data-card="saveNewTask" class="add-card" />
      <div class="table-cards">
        <div class="table-header">
          <p>Title</p>
          <p>Description</p>
          <p>Delete</p>
        </div>
        <div class="dividing-line"></div>
        <!-- <div v-for="this.tasks"> -->
          <CardTask v-for="(task, index) in tasks" :key="index" :task="task" @delete-card="deleteCard"/>
        <!-- </div> -->
      </div>
    </div>
  </div>
</template>

<script>
import AddCard from './components/AddCard.vue'
import CardTask from './components/CardTask.vue'


export default {
  name: 'App',
  data() {
    return {
      tasks : [{
        id: 1,
        title: 'Todo1',
        description: 'Description1'
      },
      {
        id: 2, 
        title: 'Todo2',
        description: 'Description1'
      },
      {
        id: 3,
        title: 'Todo3',
        description: 'Description1'
      }]
    }
  },
  components: {
    AddCard,
    CardTask
  },
  methods: {
    saveNewTask (data) {
      this.tasks.push(data)
    },
    deleteCard(task) {
        this.tasks = this.tasks.filter(entry => entry !== task)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.add-card {
  width: 20%;
}
#body-block {
  display: flex;
  flex-direction: row;
}
.table-cards {
  margin-left: 40px;
  width: 65%;
}
.table-header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.dividing-line {
  background: #2c3e50;
  height: 1px;
  width: 100%;
}
</style>
