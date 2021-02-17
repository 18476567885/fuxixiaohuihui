<template>
	<div>
        <ul class="item">
            <li v-for="(item, index) in itemArr" :key="index"
              :class="{'clickBg':index==clickIndex,'hoverBg':index==hoverIndex}"
              @click="clickIndex = index"
              @mouseover="hoverIndex = index"
              @mouseout="hoverIndex = -1">
              {{item}}
            </li>
          </ul>
    </div>
</template>
<script>
export default {
	data() {
		return {
			itemArr: ['A', 'B', 'C', 'D'],
			hoverIndex: -1, //表示当前hover的是第几个li 初始为 -1 或 null 不能为0 0表示第一个li
			clickIndex: -1, //表示当前点击的是第几个li 初始为 -1 或 null 不能为0 0表示第一个li
		}
	},
}
</script>
<style>
.hoverBg {
	background: #ccc;
	color: #fff;
}
.clickBg {
	background: red;
	color: #fff;
}
</style>
