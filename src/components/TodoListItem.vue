<template>
		<li class="todo__item">
			<span> {{item.text}} </span>
			<!-- <div>
				<input type="checkbox" :v-model="item.completed" :id="`cb_completed_${item.id}`">
				<label for="`cb_completed_${item.id}`"> {{item.text}} </label>
			</div> -->
			<button @click="deleteItem" class="btn" >Delete</button>
		</li>
</template>
<script>
	export default{		
		props: ['item',],
		
		methods: {
			deleteItem(){
				this.$emit('delete-todo-item', this.item )
			}
		}
	}
</script>

<!-- 
	Silme eventi bu componentte
	TodoListItem < TodoList < App (event/data App componentine gönderilmeli)  
	Yani child içerisindeki childtan tetikleyici bilgi alacağız

	4. satır	: click eventi atandı
	12. satır	: parent componente data aktarıldı. 'delete-todo-item'
 -->
