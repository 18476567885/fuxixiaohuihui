<template>
	<div>
		<div>
			<h3>排序</h3>
			<button  @click="orderByage(0)">默认</button>

			<button @click="orderByage(2)">年龄↑</button>
			<button  @click="orderByage(1)">年龄↓</button>
		</div>
		<h3>搜索列表</h3>
		<input type="text" placeholder="请输入搜索内容" v-model="serchName" />
		<p>============================</p>
		<ul>
			<li v-for="(p, index) in filterName" :key="index">
				{{ index + 1 }} ) 姓名：{{ p.name }};年龄：{{ p.age }};性别：{{ p.sex }} 联系：{{ p.tel }}
			</li>
		</ul>
	</div>
</template>
<script>
export default {
	data() {
		return {
			serchName: '',
			persons: [
				{ name: '张三', age: '18', sex: '女', tel: '199222222' },
				{ name: '李四', age: '28', sex: '男', tel: '199222222' },
				{ name: '赵武', age: '38', sex: '男', tel: '199222222' },
				{ name: '王柳', age: '48', sex: '女', tel: '199222222' },
				{ name: '文博', age: '22', sex: '男', tel: '199222222' },
				{ name: '覃大', age: '33', sex: '女', tel: '199222222' },
				{ name: '李会', age: '25', sex: '男', tel: '199222222' },
				{ name: '张三', age: '18', sex: '女', tel: '199222222' },
				{ name: '李四', age: '28', sex: '男', tel: '199222222' },
				{ name: '赵武', age: '38', sex: '男', tel: '199222222' },
				{ name: '王柳', age: '48', sex: '女', tel: '199222222' },
				{ name: '文博', age: '22', sex: '男', tel: '199222222' },
				{ name: '覃大', age: '33', sex: '女', tel: '199222222' },
				{ name: '李会', age: '25', sex: '男', tel: '199222222' },
				{ name: '张三', age: '18', sex: '女', tel: '199222222' },
				{ name: '李四', age: '28', sex: '男', tel: '199222222' },
				{ name: '赵武', age: '38', sex: '男', tel: '199222222' },
				{ name: '王柳', age: '48', sex: '女', tel: '199222222' },
				{ name: '文博', age: '22', sex: '男', tel: '199222222' },
				{ name: '覃大', age: '33', sex: '女', tel: '199222222' },
				{ name: '李会', age: '25', sex: '男', tel: '199222222' },
			],
            orderType:0  //作排序
        }
	},
	methods: {
		orderByage(orderType1) {
			this.orderType = orderType1
		},
	},
	computed: {
		filterName() {
			// 获取数据; 相当于 this.serchName ;this.persons
			let { serchName, persons, orderType } = this
			// 2,取出数组中的数据，展开，保证搜索之前也有数据
			let arr = [...persons]  
			// 3,过滤数组
			// 根据 serchName过滤，字符串 serchName.trim()过滤两头的空格
			if (serchName.trim()) {   // 注意：IE9以下的版本没有trim()方法
				//  数组的 filter()方法；过滤，接收一个函数， 根据条件 将对应的数据 返回
				arr = persons.filter((p) => p.name.indexOf(serchName) !== -1)  
			}
            // 4，排序
            if(orderType){
                arr.sort((p1,p2)=>{
                    if(orderType===1){
						return p2.age-p1.age
					}  //降序
                    else{
						return p1.age-p2.age

					}             //升序
                })
            }
			return arr // 相当于调用 get()方法，所以要 return
		},
	},
}
</script>
<style>
ul {
	list-style: none;
}
ul li {
	padding: 10px;
}
button {
	margin: 10px;
}
</style>
