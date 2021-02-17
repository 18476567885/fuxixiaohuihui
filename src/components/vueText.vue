<template>
	<div>
		<!-- 使用组件三部曲：1）引入组件；2）注册组件；3）标签实例化 -->
		<h3>{{ mag }}</h3>
		<h3>{{ mag.toUpperCase() }}</h3>
		
        <h3>强制数据绑定</h3>
		<a v-bind:href="site">学习vue</a>
        <!-- 简写 冒号即可 ： -->
		<a :href="site">学习vue</a>

       
        <h3>绑定事件监听</h3>
        <!-- study是一个函数 -->
         <p> <button v-on:click="study('大林')">学习vue</button></p>
         <!-- 简写 -->
         <p> <button @click="study('大林')">学习vue</button></p>

	</div>
</template>
<script>
export default {
	data() {
		return {
			mag: 'like it',
			site: 'https://www.itLike.com',
		}
	},
    methods:{
        study(name){
            alert(`祝${name},学有所成`)
        }
    }
}
</script>
