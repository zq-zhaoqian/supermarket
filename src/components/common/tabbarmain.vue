<template>
  <div id="app">
    <router-view></router-view>
    <taball class="taball">
      <tabsolt class="tab-bar" path="/home">
        <img slot='icon1' src="@/assets/img/tab-img/shouye.svg">
        <img slot='icon2' src="@/assets/img/tab-img/shouye1.svg">
        <div slot='icontest'>首页</div>
      </tabsolt>
      <tabsolt class="tab-bar" path="/fenlei">
        <img slot='icon1' src="@/assets/img/tab-img/fenlei.svg">
        <img slot='icon2' src="@/assets/img/tab-img/fenlei1.svg">
        <div slot='icontest'>分类</div>
      </tabsolt>
      <tabsolt path="/faxian" class="tab-bar" >
        <img slot='icon1' src="@/assets/img/tab-img/faxian.svg">
        <img slot='icon2' src="@/assets/img/tab-img/faxian1.svg">
        <div slot='icontest'>发现</div>
      </tabsolt>
      <tabsolt class="tab-bar" path='/wode'>
        <img slot='icon1' src="@/assets/img/tab-img/wode.svg">
        <img slot='icon2' src="@/assets/img/tab-img/wode1.svg">
        <div slot='icontest'>我的</div>
      </tabsolt>
    </taball>
  </div>
</template>

<script>
import taball from './tabbarCommon/taball.vue'
import tabsolt from './tabbarCommon/tabsolt.vue'
export default {
  components: { taball,tabsolt},
  name: 'App'

  
  
}
</script>

<style>
*{
  margin: 0px;
  padding: 0px;
}
.taball{
  display: flex;
  height: 49px;
  width: 100%;
  text-align: center;
  background-color: #f6f6f6;
  border-top:1px solid #e1e1e1;
  position: absolute;
  bottom: 0;
}
.taball .tab-bar{
  flex: 1;
}
.tab-bar img{
  width: 24px;
    margin-top: 2px;
}
.tab-bar{
  font-size: 10px;
}
</style>
