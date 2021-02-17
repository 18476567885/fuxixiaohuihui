<template>
	<div>
		<h3>格式化人民币</h3>
		<p>{{ money | moneyFom }}</p>
		<p>{{ page | moneyFom }}</p>

		<h3>格式化日期</h3>
		<p>{{ time | timeFomat }}</p>
	</div>
</template>
<script>
import moment from 'moment'
export default {
	data() {
		return {
			money: 22345,
			page: 122223.764,
			time: new Date(),
		}
	},
	mounted() {
		setInterval(() => {
			this.time = new Date()
		}, 1000)
	},
	// 局部过滤器（当前组件）
	filters: {
		moneyFom(vavlue) {
			return '￥' + Number(vavlue).toFixed(2)
		},
		timeFomat(value, format = 'YYYY-MM-DD HH:mm:ss') {
			return moment(value).format(format)
		},
	},
}
</script>
