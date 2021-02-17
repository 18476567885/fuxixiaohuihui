<template>
	<div>
		<p>姓名：{{ name }}</p>
		<p>年龄：{{ age }}</p>
		<p>{{ person }}</p>
   <button @click="logPerson"> 调用方法</button>
	</div>
</template>
<script>
export default {
	data() {
		return {}
	},
	props: {          //接收 父组件的数据
		name: String,   //定义传递的类型
		age: Number,
        person:Object,
        logPerson:Function  //传递方法
	},
}
</script>
