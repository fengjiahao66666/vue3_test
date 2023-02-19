<template>
	<div class="app">
		<h3>我是App组件</h3>
		<Child/>
	</div>
</template>

<script>
/*eslint-disable*/
	import Child from './components/Child'
	import Son from './components/Son.vue';
	export default {
		name:'App',
		components:{Child,Son},
		
	}
</script>
<style>
    .app{
	    background-color: gray;
	    padding: 10px;
	}
</style>