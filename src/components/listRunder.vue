<template>
	<div>
		<h3>遍历数组</h3>
		<ul>
			<li v-for="(person, index) in persons" :key="index">
			{{index}} )	姓名：{{ person.name }},年龄：{{ person.age }},性别：{{ person.sex }},
			</li>
		</ul>
	</div>
</template>
<script>
export default {
	data() {
		return {
			persons: [
				{ name: '张三', age: '18', sex: '男' },
				{ name: '李四', age: '28', sex: '男' },
				{ name: '王五', age: '38', sex: '女' },
				{ name: '赵六', age: '48', sex: '女' },
			],
		}
	},
}
</script>
<style>
  ul{
      list-style: none;
  }
</style>
