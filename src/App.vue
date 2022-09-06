<template>
  <div class="container">
    <h2 class="todo-title">Todo List Using Vue JS</h2>
    <div class="todo-card">
      <AddSection @send-todo-text="addNewTodo" />
      <TodoList :todoListData="todoList" @delete-todo-item="deleteItem"/>
      <ResultBar  :todoListDataCount="todoList" />
    </div>
  </div>
</template>
<script>
import AddSection from '@/components/AddSection.vue';
import TodoList from './components/TodoList.vue';
import ResultBar from './components/ResultBar.vue';
export default {
  components: {
    AddSection,
    TodoList,
    ResultBar
  },
  data() {
    return {
      todoList: [
        { id: 1, text: "Todo 1", completed: false },
        { id: 2, text: "Todo 2", completed: false },
        { id: 3, text: "Todo 3", completed: false },
        { id: 4, text: "Todo 4", completed: false },
        { id: 5, text: "Todo 5", completed: false },
        { id: 6, text: "Todo 6", completed: false },
      ]
    };
  },
  methods: {
    deleteItem(todoItem) {
      this.todoList = this.todoList.filter(d => d !== todoItem);
    },
    addNewTodo(data) {
      this.todoList.push({ id: new Date().getTime(), text: data, completed: false });
    },
  },

}
</script>
<!-- 
	5-6-7 satır 	: App.vue componenti 3 alt componentten oluşur. AddSection-TodoList-ResultBar
	6. satır    	: alt componente props gönderimi
                  todoListData isminde props oluşturuldu.
                  oluşturulan propsun datası todoList arrayidir. (23. satır)

  37. satır     : data AddSectiondan gelen veridir.

  6. satır      : TodoListItem < TodoList gelen data/event kullanıldı.
 -->

 <!-- 
  computed: {
  completedItemCount(){
    return this.todoList.filter((t) => t.completed).length;
  },
  unCompletedItemCount(){
    return this.todoList.filter(t => !t.completed).length;
  },

<ResultBar  :todoListDataCount="todoList" 
          :itemCount="completedItemCount" 
          :unItemCount="unCompletedItemCount"/>
} -->