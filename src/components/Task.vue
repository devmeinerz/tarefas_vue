<template>
  <div id="task">
    <form @submit="addItem">
      <input type="text" placeholder="Tarefa de hoje:" v-model="tarefa" />
      <button type="submit">Adicionar</button>
    </form>
    <Item :Lista="tarefas"/>
  </div>
</template>

<script>
import Item from "./Item.vue";
export default {
  name: "Task",
  components: {
    Item,
  },
  data() {
    return {
      tarefa: "",
      tarefas: [],
    };
  },
  methods: {
    addItem(a) {
      a.preventDefault();
      if (this.tarefa == "") {
        alert("Preencha os campos abaixo");
        return;
      } else {
        this.tarefas.push({
          text: this.tarefa,
          key: Date.now(),
        });
      }
      this.tarefa = "";
    },
  },
};
</script>

<style scoped>
#task {
  max-width: 700px;
  background: #ffffff;
  border-radius: 10px;
  padding: 20px;
  margin: 20px auto;
  box-shadow: 0 0 5px #00000048;
}
form {
  margin-top: 20px;
  display: flex;
  flex-direction: row;
  justify-content: center;
}
input {
  flex: 1;
  border: 1.5px solid #b1d3bc;
  padding: 6px 10px;
  border-radius: 5px;
  font-size: 14px;
  outline: none;
}
form button {
  cursor: pointer;
  padding: 10px;
  border-radius: 5px;
  margin-left: 20px;
  background: #3b8654;
  color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
