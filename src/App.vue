<template>
  <div id="app">
    <router-view/>
    <van-tabbar v-model="active" :z-index="10">
      <van-tabbar-item
        v-for="(tab, index) in tabs"
        :key="index"
        :to="tab.to"
      >
        <span>{{tab.text}}</span>
        <img
          slot="icon"
          slot-scope="props"
          :src="props.active ? tab.active : tab.normal"
        >
      </van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
       active: 0,
      tabs: [
        {
          to: '/',
          text: '外卖',
          normal: require('../static/tabbar/home.png'),
          active: require('../static/tabbar/home_active.png')
        },
        {
          to: '/list',
          text: '订单',
          normal: require('../static/tabbar/list.png'),
          active: require('../static/tabbar/list_active.png')
        },
        {
          to: '/find',
          text: '发现',
          normal: require('../static/tabbar/find.png'),
          active: require('../static/tabbar/find_active.png')
        },
        {
          to: '/mine',
          text: '我的',
          normal: require('../static/tabbar/mine.png'),
          active: require('../static/tabbar/mine_active.png')
        }
      ],
    }
  }
}
</script>

<style lang='less' scoped>
#app {

}
</style>
