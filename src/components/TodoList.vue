<template>
	<ul class="todo__list">
		<TodoListItem 	v-for="todoItem in todoListData" 
						:key="todoItem.id" 
						:item="todoItem"
						@delete-todo-item="$emit('delete-todo-item', $event)"
						/> 
	</ul>
</template>
<script>
	import TodoListItem from "./TodoListItem.vue";
	export default {
		components: {
			TodoListItem
		},
		props: ["todoListData",],

	}
</script>
<!-- 
	3. - 4. satır 	: parent componentten (App) gelen propsu kullanma
	5. satır 		: child componente (TodoListItem) props gönderme
	15. satır		: parent componentten (App) gelen propsları alma

	6. satır	: child componenten gelen data parent componente aktarıldı.
	$event   	: alt componentten gelen data demek.
 -->