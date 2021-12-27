<template>
  <div id="item">
    <ul>
      <li v-for="task in lista" :key="task.key">
        <span>{{ task.text }}</span>
        <button @click="deleteItem(task.key)">Concluir</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: ["lista", "delete"],
  methods: {
    deleteItem(key){
      this.delete(key);
    },
  },
};
</script>

<style scoped>
#item {
  white-space: pre-wrap;
  word-wrap: break-word;
}
ul {
  list-style: none;
  padding: 0;
  margin-top: 20px;
}
ul li {
  padding: 15px 0;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
li:not(:first-child) {
  border-top: 2px solid #eee;
}
span {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #202020;
}
button {
  cursor: pointer;
  padding: 4px 10px;
  border-radius: 5px;
  margin-left: 20px;
  background: #919191;
  color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>