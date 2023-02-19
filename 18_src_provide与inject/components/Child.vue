<template>
	<div class="child">
		<h3>我是Child组件（子）{{x.name}}--{{x.price}}</h3>
		<Son/>
	</div>
</template>

<script>
/*eslint-disable*/
	import {inject} from 'vue'
	import Son from './Son.vue'
	export default {
		name:'Child',
		components:{Son},
		setup(){
			let x = inject('car')
			console.log(x,'Child-----')
			return {x}
		} 
	}
</script>

<style>
	.child{
		background-color: skyblue;
		padding: 10px;
	}
</style>