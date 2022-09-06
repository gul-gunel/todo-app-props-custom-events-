<template>
	<div class="todo__add">
		<input v-model="todoText" @keydown.enter="addNewTodoChild" class="todo__input" type="text" placeholder="Add task...">
		<button @click="addNewTodoChild" class="btn btn--blue">Add</button>
	</div>
</template>
<script>
	export default{
		data(){
			return{
				todoText: null,
			}
		},
		methods: {
			addNewTodoChild(){
				this.$emit('send-todo-text', this.todoText);
				this.todoText = null;
			}
		}
	}
</script>
<!-- 
	Bu componetteki (AddSection - Child) imputtan alınan data > parent (App) componente iletilmeli
	App componentinde todoList arrayine push edilmeli.
	Child  >>  Parent şeklindeki veri aktarımı Custom Event olarak isimlendirilir.  
	$emit ile event üretilir.

	16. satır	: parent componentine gönderilecek datanın adı 'send-todo-text'
		gönderilecek data eventtir.
		bu isimle parent componente gelir.
 -->