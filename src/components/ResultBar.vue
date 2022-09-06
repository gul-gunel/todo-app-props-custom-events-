<template>
	<div class="todo__result">
		<small>Total number of missions {{todoListDataCount.length}} </small>
		<!-- <small>Number of task {{itemCount}} </small>
		<small>Number of task {{unItemCount}} </small> -->
	</div>
</template>
<script>
export default {
	props: ['todoListDataCount', 'itemCount', 'unItemCount' ],
}
</script>
