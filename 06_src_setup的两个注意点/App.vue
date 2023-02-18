<template>
	<demo @hello="showHelloMsg" msg="你好啊" school="尚硅谷">
		<template v-slot:qwe>
			<span>尚硅谷</span>
		</template>
		<template v-slot:asd>
			<span>尚硅谷</span>
		</template>
	</demo>
</template>

<script>
    import Demo from './components/Demo.vue'
	// import {reactive} from 'vue'
	export default {
		name: 'App',
		components:{Demo},
		setup(){
			function showHelloMsg(value){
				alert(`你好啊，你出发了hello事件，我收到了参数是：${value}`)
			}
			return {
				showHelloMsg
			}
		}
	}
</script>

