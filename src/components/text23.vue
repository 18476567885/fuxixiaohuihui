<template>
	<div>
		<ul>
			<li v-for="(p, index) in persons" :key="index">
				{{ index }}) {{ p }}
				<button @click="lister(p)">++</button>
			</li>
		</ul>
	</div>
</template>
<script>
// 创建一个数据，这个数据有三四个对象，对象有两个属性，一个name，字符串类型随便写，
// 另一个字段是count ，数字类型，也是随便写，点击按钮，当前的这个count++
export default {
	data() {
		return {
			persons: [
				{ name: '张三', count: 18, state: 'false' },
				{ name: '李四', count: 28, state: 'false' },
				{ name: '王五', count: 38, state: 'false' },
				{ name: '赵六', count: 48, state: 'false' },
			],
		}
	},
	methods: {
		lister(jia) {
			jia.count++

			jia.state = !jia.state
		},
	},
}
</script>
