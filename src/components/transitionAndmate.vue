<template>
	<div>
		<h3>过渡效果</h3>
		<!-- 过渡的内容 外面用transition标签包裹 -->
		<button @click="show = !show">切换</button>

		<transition name="fade">
			<div class="box" v-if="show">心想事成</div>
		</transition>
		<p>==============================</p>
		<h3>动画</h3>
		<button @click="flag = !flag">显示与隐藏</button>
		<transition name="banner">
			<img :src="pic" alt="" v-if="flag" />
		</transition>
	</div>
</template>
<script>
import pic from '@/assets/logo.png'
export default {
	data() {
		return {
			show: false,
			pic: pic,
			flag: true,
		}
	},
	
}
</script>
<style>
.box {
	width: 200px;
	height: 200px;
	background-color: red;
	color: #fff;
	font-size: 20px;
	display: flex;
	justify-content: center;
	align-items: center;
}
.fade-enter,
.fade-leave-to {
	opacity: 0;
	transform: translateX(200px);
}
.fade-enter-active,
.fade-leave-active {
	transition: all 2s ease-in-out;
}
</style>
