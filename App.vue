<template>
  <header>
    <h2>To Do List</h2>
  </header>
  <div class="container">
    <input type="text" v-model="newTask" placeholder="enter the mission" @keydown.enter.prevent="addtoList">
    <button @click="addtoList()">Add List</button>
  </div>
  <div class="list">
    <li v-for="(task, index) in tasks">{{ task }}
      <button class="remove" @click="removetheList(index)">X</button>
    </li>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
      tasks: []
    }
  },
  methods: {
    addtoList() {
      if (this.newTask !== "") {
        this.tasks.push(this.newTask)
      }
    }, removetheList(index) {
      this.tasks.splice(index, 1)
    }
  }
}
</script>
<style>
* {
  padding: 0;
  margin: 0;
}

header {
  color: white;
  padding: 20px;
  background-color: rgb(169, 78, 45);
  display: flex;
  justify-content: center;
  width: 50%;
  margin: auto;
  border-radius: 0px 0px 20px 20px;
}

.container {
  width: 100%;
  display: flex;
  margin: auto;
  justify-content: center;
}

input {
  width: 35%;
  padding: 1rem;
  border: 1px solid #a9a9a970;
  border-radius: 20px 20px 20px 20px;
  margin: 5px;
}

button {
  border: 1px solid #a9a9a970;
  width: 150px;
  padding: 1rem;
  margin: 5px;
  height: 50px;
  border-radius: 20px;
}

.li {
  display: flex;
  justify-content: center;
}

li {
  color: #7d7a7a;
  list-style-type: none;
  width: 40%;
  margin: auto;
}

.remove {
  border: none;
  padding: none;
  width: none;
  height: none;
  color: red;
}
</style>