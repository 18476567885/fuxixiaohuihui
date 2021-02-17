<template>
	<div class="hello">
		<label for="">
			姓：<input type="text" placeholder="请输入姓" v-model="firstName" />
			<p></p>
		</label>
		<label for="">
			名： <input type="text" placeholder="请输入名" v-model="lastName" />
			<p></p>
		</label>
		<label for="">
			<!-- 单向绑定 -->
			姓名： <input type="text" placeholder="请输入姓名" v-model="fullName" />
			<p></p>
		</label>
		<label for="">
			<!-- 双向绑定 -->
			姓名： <input type="text" placeholder="请输入姓" v-model="fullNametwo" />
			<p></p>
		</label>
    <label for="">
			姓名： <input type="text" placeholder="请输入姓" v-model="fullNameTree" />
			<p></p>
		</label>
	</div>
</template>
<script>
export default {
	name: 'HelloWorld',
	data() {
		return {
			firstName: '',
			lastName: '',
      // 被watch监听改变
      fullNameTree:"",
		}
	},
  // 
	computed: {
		// 计算属性 内置有 get 和 set方法
    // 栗子 姓+名
		// 本质是函数 get() 方法; 是取值
    // 简写
		fullName() {
			return this.firstName + '.' + this.lastName
		},
    // 双向绑定
		fullNametwo: {
			get() {
				console.log('调用了fullnametwo的getter方法');
        return this.firstName + '.' + this.lastName

			},
      // set会有 传值
			set(value) {
        // 1,更新 firstName 和lastName
        // 分割和赋值
     let names=value.split(".");
				console.log(names);

     this.firstName=names[0];
     this.lastName=names[1];
      },
		},
	},
  watch:{
    // 监听 firstName，发生改变 通过 value体现
    firstName(value){
    // console.log(`watch监听到firstName发生改变,${value}`);
    // 更新 firstNameTree
    this.fullNameTree=value+"."+this.lastName
    },
    // 监听lastName
  lastName(value){
    // console.log(`watch监听到firstName发生改变,${value}`);
    this.fullNameTree=this.firstName+'.'+value

  }
  }
}
</script>
