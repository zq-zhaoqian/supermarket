<template>
    <div class="tabsolt" @click = 'gohome'>
    <!-- <img src="../../assets/img/shouye.svg">
    <div class="icon-test">首页</div> -->
    <slot name='icon1' class="icon" v-if='isActive'></slot>
    <slot name='icon2' class="icon" v-else></slot>
    <div :class={active:!isActive}><slot name='icontest' ></slot></div>
    </div>
</template>
<script>
export default {
    name:'tabsolt',
    props:{
       path:String
    },
    data(){
        return{
            // isActive:true 
            }
    },
    computed:{
        isActive(){
            return this.$route.path.indexOf(this.path) == -1//在活跃的路由搜索传过来的path，搜索不到则返回-1，若返回不等于-1则说明两边path一致
        }
    },
    methods:{
    gohome(){
     this.$router.replace(this.path)
    console.log(this.path);
    }
  }
}

//练习promise.链式编程（一步一步执行操作）
new Promise((resolve,reject)=>{//创建一个promise,promise的两个参数resolve,reject实际都为函数
    setTimeout(()=>{//创建一个延时器函数;也可以理解为向服务器发送一个请求
        resolve('hoello')//获取一个数据成功
    },1000)//延时1秒获取
}).then((data)=>{//在promise中发送请求，以及获取的数据，都可以在then((data)=>{})中操作,data为在peomise中获取的参数
    console.log(data);
    return new Promise((resolve,reject)=>{//在then里面再创建一个promise，可以在以获取到的数据继续发送请求
        setTimeout(()=>{
            // resolve('thinks');
            reject('nonono')
        },2000)
    })
}).then((data)=>{
    console.log(data);
}).catch((rej)=>{//获取或发送请求失败则显示catch的信息
    console.log(rej);
})

//promise的简写方法
new Promise((resolve,reject)=>{
    setTimeout(()=>{
        resolve('张三');
        
    })
}).then((data)=>{
console.log(data);
return data + '111'//只传参数时，可省略的new promis（（resolve，reject）=>{...}）
}).then((data1)=>{
console.log(data1);
})

//promise.all的使用方法，等于全部数据请求成功后才会执行的操作
Promise.all([//打包一些异步请求，以数组形式
    new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve({name:'张三',age:18})
        })
    }),
    new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve({name:'李四',age:26})
        })
    })
]).then(data=>{//data指的是所有resolve的数据
    console.log(data);
})
</script>
<style>
.active{
    color: blue;
}
</style>