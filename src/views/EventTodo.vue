<template>
  <div>
    <input type="text" v-model="todo">
    <button v-on:click="addTodo()">추가</button>
  </div>
  <div>
    <ul v-for="(todo, idx) in todoList" :key="idx">
      <li>{{ idx + 1 }} {{ todo.text }}{{ idx + 1 }}</li>
      <button v-on:click="delTodo(todo.no)">삭제</button>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      todo: { no: 3, text: '그담할일' },
      todoList: [{ no: 1, text: '할일' }, { no: 2, text: '할일' }]
    }
  },
  methods: {
    addTodo() {
      let no, text;
      no = this.todoList[this.todoList.length - 1].no +1;
      text = this.todo;
      this.todoList.splice(no - 1, 0, { no, text });
      this.todo = '';
    },
    delTodo(no) {
      console.log('no', no);
      this.todoList = this.todoList.filter(todo => todo.no == no ? false : true);
    }
  }
}
</script>
