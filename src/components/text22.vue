<template>
    <div>
        <ul>
            <li v-for="(p,index) in persons" :key="index" @click="click(index)"
            :class="active==index? 'yanse':''">
              {{index}})  {{p}} 
            </li>
        </ul>
    </div>
</template>
<script>
    // 写一个列表，每个列表有一个按钮，点击这个按钮获取这个列表的index
    export default{
        data(){
            return{
                active:"-1",
          persons:[
          { name: '张三', age: '18', sex: '男' },
				{ name: '李四', age: '28', sex: '男' },
				{ name: '王五', age: '38', sex: '女' },
				{ name: '赵六', age: '48', sex: '女' },
          ]
            }
        }
    ,methods:{
        click(index){
            // 点击哪个选项，将他的值赋予给属性 active的值 
          this.active=index;
          console.log(this.active);
          
        }
    }
    }
</script>
<style>
    .yanse{
        color: red;
    }
</style>