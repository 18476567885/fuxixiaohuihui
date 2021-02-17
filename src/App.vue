<template>
	<div id="app">
		<!-- <img alt="Vue logo" src="./assets/logo.png"> -->
		<!-- 除了字符串，其他类型都需要 动态绑定 -->
		<zujiantongx name="小辉辉" :age="26" :person="p" :logPerson="logPerson"/>
	</div>
</template>

<script>
import zujiantongx from './components/zujiantongx.vue'
export default {
	name: 'App',
	components: {
		// 引用组件三步走
		// 引用，注册，标签实例化使用
		zujiantongx,
	},
	data() {
		return {
			p: {
				name: '林正英',
				age: 100,
			},
		}
	},
	methods: {
		logPerson() {
			console.log('今晚喝酒！！')
		},
	},
}
</script>

<style></style>
