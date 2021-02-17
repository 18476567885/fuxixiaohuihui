<template>
	<div>
		<ul>
			<li v-for="(item, index) in items" :key="index" @click="itemClick(index)"
             :class="active == index ? 'red' : ''">
				{{ index }}) {{ item }}
			</li>
		</ul>
	</div>
</template>
<script>
// 实现这样的一个需求：使用v-for生成一个列表，
// 点击列表中的某个元素，该元素改变其样式（也就是字体变红），其它元素不变


// 通过设置一个点击事件btnClick(index)获取点击元素的下标，
//     将被点击的元素的下标与列表中元素进行匹配，相等的进行css渲染，

//     这样就避免了其它元素全部一起渲染。
// 这里的active设置为-1，是因为如果是0或空的话，
// 第一个元素就默认被渲染了样式，也就是变红色

export default {
	data() {
		return {
			items: ['喜羊羊', '美羊羊', '懒洋洋', '红太狼', '灰太狼'],
			active: 0,
		}
	},
	methods: {
		itemClick(index) {
			this.active = index
		},
	},
}
</script>
<style>
.red {
	color: red;
}
</style>
