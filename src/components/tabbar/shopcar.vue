<template>
    <div class="box">
      <transition
      @before-enter="beforeEnter"
      @enter="enter"
      @after-enter="afterEnter">
        <div class="qiu" v-show="ballFlag" ref="ball"></div>
      </transition>
      <button @click="addshow">加入购物车</button>
    </div>
  </template>
  
  <script>
  export default {
    data () {
      return {
        ballFlag:true
      }
    },
    methods: {
      addshow(){
        this.ballFlag = !this.ballFlag
      },
      beforeEnter(el){
        el.style.transform = "translate(0,0)"
      },
      enter(el,done){
        el.offsetWidth
        const ballPosition = this.$refs.ball.getBoundingClientRect()
        const badgePosition = document.getElementById('badge').getBoundingClientRect()
        
        const xdis = badgePosition.left-ballPosition.left
        const ydis = badgePosition.top-ballPosition.top

        console.log(xdis,ydis);
        el.style.transform = "translate("+ xdis +"px,"+ ydis +"px)"
        el.style.transition = "all .5s cubic-bezier(.4,-0.3,1,.68)"
        done()
      },
      afterEnter(el){
        this.ballFlag = !this.ballFlag
      }
    },
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  .box{
    height: 1000px;
  }
  .qiu{
    width: 15px;
    height: 15px;
    border-radius: 50%;
    background-color: red;
    position: absolute;
    z-index: 99;
    top: 290px;
    left: 146px;
  }

  button{
    position: absolute;
    top: 340px;
    left: 120px;
  }
  </style>