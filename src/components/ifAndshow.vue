<template>
	<div>
		<div v-if="flag">今晚学习</div>
		<div v-else>今晚不学习</div>
		<button @click="flag = !flag">切换</button>
		<p>===============</p>
		
        <div v-show="flag">今晚学习</div>
		<div v-show="!flag">今晚不学习</div>
		<button @click="flag = !flag">切换</button>
		
        <p>=====================</p>
		<!-- v-if和v-show  区别 -->
        <!-- v-if 会在标签那里添加，或删除 -->
        <!--  v-show 会全部创建出来， -->
	</div>
</template>
<script>
export default {
	data() {
		return {
			flag: true,
		}
	},
}
</script>
