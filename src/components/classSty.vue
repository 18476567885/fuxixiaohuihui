<template>
	<div>
		<h3>class的使用</h3>
		<div :class="oneClass">样式类可以是字符串</div>

		<div :class="{ calssTwo: true }">样式类可以是对象</div>
		<!-- 样式类是对象时 是键值对的形式出现  true显示，false不显示-->

		<div :class="[oneClass, 'calssTwo']">样式类可以是数组</div>
		<p>================</p>
		<h3>style的使用</h3>
		<div style="width: 200px;height: 200px;margin: 10px auto;" :style="{backgroundColor:bgcolor}">
			style的使用
		</div>
	</div>
</template>
<script>
export default {
	data() {
		return {
			oneClass: 'calssOne',
			twoClass: 'calssTwo',
			bgcolor: 'red',
		}
	},
}
</script>
<style>
.calssOne {
	font-size: 20px;
	color: red;
}
.calssTwo {
	width: 200px;
	height: 200px;
	background-color: sandybrown;
	margin: 10px auto;
}
</style>
