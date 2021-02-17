<template>
	<div>
		<h1>
			{{ countmoney }}
		</h1>
		<h3>{{ relted }}</h3>
		<button @click="click">增加</button>
		<p></p>
		<button @click="jianjian">减少</button>
		<p></p>
	</div>
</template>
<script>
export default {
	data() {
		return {
			count: '50',
		}
	},
	computed: {
		countmoney() {
			return this.count + '$'
		},
		relted() {
			if (this.count >= 60 && this.count < 90) {
				return '合格'
			} else if (this.count < 60) {
				return '不及格'
			} else if (this.count >= 90) {
				return '优秀'
			}
		},
	},

	methods: {
		click() {
			this.count++
		},
		jianjian() {
			this.count--
		},
	},
}
</script>
