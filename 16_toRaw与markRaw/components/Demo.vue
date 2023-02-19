<template>
	<h4>当前的求和为：{{ sum }}</h4>
	<button @click="sum++">点我+1</button>
	<hr>
	<h2>姓名：{{name}}</h2>
	<h2>年龄：{{age}}</h2>
	<h2>薪资：{{job.j1.salary}}K</h2>
	<h3 v-show="person.car">座驾信息:{{ person.car }}</h3>
	<button @click="name+='~'">修改姓名</button>
	<button @click="age++">增长年龄</button>
	<button @click="job.j1.salary++">涨薪</button>
	<button @click="showRawPerson">输出最原始的person</button>
	<button @click="addCar">给人添加一台车</button>
	<button @click="person.car.name+='!'" v-show="person.car">换车名</button>
	<button @click="person.car.price++" v-show="person.car">换价格</button>
</template>

<script>
/*eslint-disable*/
	import {ref,reactive,toRefs, toRaw, markRaw} from 'vue'
	export default {
		name: 'Demo',
		setup(){
			//数据
			let sum = ref(0)
			let person = reactive({
				name:'张三',
				age:18,
				job:{
					j1:{
						salary:20
					}
				}
			})
			function showRawPerson(){
				const p = toRaw(person) //只限reactive定义的
				p.age++
				console.log(p);
			}
			function addCar(){
				let car = {name:'奔驰',price:40}
				person.car = markRaw(car)
			}
			
			//返回一个对象（常用）
			return {
				person,
				addCar,
				showRawPerson,
				sum,
				...toRefs(person)
			}
		}
	}
</script>

