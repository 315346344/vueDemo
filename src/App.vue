<template>
  <div id="app" class="app-container">
    <!-- 顶部 -->
    <mt-header fixed title="标题">
      <a ref="#" slot="left" @click="gogo" v-show="flag">
        <mt-button icon="back">返回</mt-button>
      </a>
    </mt-header>
    <!-- 内容 -->
    <transition >
        <router-view></router-view>
    </transition>
    <!-- 底部 -->
    <nav class="mui-bar mui-bar-tab">
        <router-link class="mui-tab-item" to="/home">
          <span class="mui-icon mui-icon-home"></span>
          <span class="mui-tab-label">首页</span>
        </router-link>
        <router-link class="mui-tab-item" to="/member">
          <span class="mui-icon mui-icon-contact"></span>
          <span class="mui-tab-label">会员</span>
        </router-link>
        <router-link class="mui-tab-item" to="/shopcar">
          <span class="mui-icon mui-icon-extra mui-icon-extra-cart"><span class="mui-badge" id="badge">0</span></span>
          <span class="mui-tab-label">购物车</span>
        </router-link>
        <router-link class="mui-tab-item" to="/search">
          <span class="mui-icon mui-icon-search"></span>
          <span class="mui-tab-label">搜索</span>
        </router-link>
      </nav>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        flag: false
      }
    },
    methods: {
      gogo(){
        this.$router.go(-1)
      }
    },
    created () {
      this.$route.path === '/home'? this.flag = flase : this.flag = true
    },
    watch: {
      '$route.path':function(newVal){
        if (newVal != '/home') {
          this.flag = true
        }else{
          this.flag = false
        }
      }
    },
  }
</script>

<style scoped>
.app-container{
  padding-top: 40px;
  overflow-x: hidden;
}

.router-link-active{
  color: red
}

.v-enter{
  opacity: 0;
  transform: translateX(100%);
}

.v-leave-to{
  opacity: 0;
  transform: translateX(-100%);
  position: absolute;
}

.v-enter-active,
.v-leave-active{
  transition: all .5s ease; 
}
</style>
