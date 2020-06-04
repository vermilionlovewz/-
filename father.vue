//父组件
// 父组件通过prop向子组件传递数据，自定义的标题和内容使用这样的场景。v-bind  ：
// 父组件还可以通过$ref向子组件传递数据，不过ref主要侧重于索引，调用子组件的属性和方法。ref用在dom元素的时候相当于选择器的作用。
<template>
    <div>
        <h1>这是父组件</h1>
        <child message="静态数据" :message2="hhh" ref="mes" @getchilid="childnews"/>
    </div>
</template>
<script>
import child from "child.vue"
export default {
    componet:{child},
    mounted:function(){
        this.$refs.mes.getmessge('获取子组件的属性和方法传递数据')
    },
    data(){
        return{
            hhh:"父组件动态传递数据",
            title:""
        }
    },
    methods:{
        childnews(x){
            this.title=x
        }
    }
}
</script>