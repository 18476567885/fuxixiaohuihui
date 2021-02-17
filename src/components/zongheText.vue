<template>
	<div>
		<div>
			<span>姓名：</span>
			<input type="text" v-model="newPerson.name" />
		</div>
		<div>
			<span>年龄：</span>
			<input type="text" v-model="newPerson.age" />
		</div>
		<div>
			<span>性别：</span>
			<select v-model="newPerson.sex">
				<option value="男">男</option>
				<option value="女">女</option>
			</select>
		</div>
		<div>
			<span>电话：</span>
			<input type="text" v-model="newPerson.tel" />
		</div>
		<div>
			<button @click="createdNew">创建新用户</button>
		</div>
		<tbody>
			<tr v-for="(p, index) in persons" :key="index">
				<td>{{ p.name }}</td>
				<td>{{ p.age }}</td>
				<td>{{ p.sex }}</td>
				<td>{{ p.tel }}</td>
				<td><button @click="del(index)">删除数据</button></td>
			</tr>
		</tbody>
	</div>
</template>
<script>
export default {
	data() {
		return {
			persons: [
				{ name: '张三', age: '18', sex: '女', tel: '199222222' },
				{ name: '李四', age: '28', sex: '男', tel: '199222222' },
				{ name: '赵武', age: '38', sex: '男', tel: '199222222' },
				{ name: '王柳', age: '48', sex: '女', tel: '199222222' },
				{ name: '文博', age: '22', sex: '男', tel: '199222222' },
				{ name: '覃大', age: '33', sex: '女', tel: '199222222' },
			],
			newPerson: { name: '', age: '', sex: '女', tel: '' },
		}
	},
	methods: {
		createdNew() {
			// 获取数据
			let { name, age, sex, tel } = this.newPerson
			// 验证操作
			if (name === '') {
				alert('名字不正确')
				return
			}
			if (age === '') {
				alert('年龄不正确')
				return
			}
			if (tel === '') {
				alert('电话不正确')
				return
			}
			// 添加到列表
			this.persons.unshift(this.newPerson)
			// 清空输入框
			this.newPerson = { name: '', age: '', sex: '女', tel: '' }
		},
		// 删除数据

		del(index) {
            // 数组的方法，删除，条件是下标，1为删除的个数
            this.persons.splice(index,1)
        },
	},
}
</script>
<style>
.class {
	margin: 0 auto;
}
</style>
