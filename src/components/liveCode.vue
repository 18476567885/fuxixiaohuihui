<template>
	<div></div>
</template>
<script>
export default {
	beforeCreate() {
        // 表示实例创建出来之前，vue实例挂载的 $el ,和data()都为undefined,还未初始化
        console.log("1");
    },
	data() {
		return {}
	},
	methods: {},
	created() {
         //创建完成后，这里可以操作 data()里面的数据，但dom未生成，所以 $el未存在
         console.log(2);
    },
      beforeMounte(){
        // 挂载之前  vue 实例的 $el 和data()都已经初始化，为虚拟的dom节点，模板在内存中，
        // 还没渲染到页面
      },
      mounted(){
        //   Vue实例挂载完成，data.message成功渲染在页面，内存模板成功挂载到页面
        // 可以看到渲染后的页面，实例创建期间最后一个生命周期函数，表示vue创建完成
      },
      beforeUpdate(){
        //   更新前，data发生变化，会触发，但未与页面数据同步
      },
      updated(){
        //   更新红，data 发生变化，触发，页面与data数据保持同步
      },
      beforDestory(){
        //  销毁前； 组件销毁之前调用，这一步，vue实例仍能使用
      },
      destory(){
        //   销毁后；组件销毁之后调用，data的改变不会触发 生命周期函数，vue实例解除事件监听和dom绑定
        // 但dom结构依然存在
      }
}
</script>
