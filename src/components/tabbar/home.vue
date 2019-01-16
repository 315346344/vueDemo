<template>
  <div>
    <!-- 轮播图 -->
    <mt-swipe :auto="4000">
      <mt-swipe-item>
        <div>1</div>
      </mt-swipe-item>
      <mt-swipe-item>
        <div>2</div>
      </mt-swipe-item>
      <mt-swipe-item>
        <div>3</div>
      </mt-swipe-item>
    </mt-swipe>
    <!-- 九宫格 -->
    <ul class="mui-table-view mui-grid-view mui-grid-9">
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="/home/newslist">
          <!-- <span class="mui-icon mui-icon-phone"></span> -->
          <img src="../../images/menu1.png" alt="">
          <div class="mui-media-body">新闻资讯</div>
        </router-link></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
          <img src="../../images/menu2.png" alt="">
          <div class="mui-media-body">新闻分享</div>
        </router-link></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
          <img src="../../images/menu3.png" alt="">
          <div class="mui-media-body">商品购买</div>
        </router-link></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
          <img src="../../images/menu4.png" alt="">
          <div class="mui-media-body">留言反馈</div>
        </router-link></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
          <img src="../../images/menu5.png" alt="">
          <div class="mui-media-body">视频专区</div>
        </router-link></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
          <img src="../../images/menu6.png" alt="">
          <div class="mui-media-body">联系我们</div>
        </router-link></li>
    </ul>
  </div>
</template>

<script>
  export default {
    data() {
      return {

      }
    },
    // created() {
    //   this.$axios.get('http://www.escook.cn:3000/api/getnewslist')
    //     .then(function (response) {
    //       console.log(response);
    //     })
    //     .catch(function (error) {
    //       console.log(error);
    //     });
    // }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .mint-swipe {
    height: 200px;
  }

  .mint-swipe-item:nth-child(1) {
    background-color: yellow;
  }

  .mint-swipe-item:nth-child(2) {
    background-color: skyblue;
  }

  .mint-swipe-item:nth-child(3) {
    background-color: pink;
  }

  .mint-swipe-item>div {
    font-size: 60px;
    position: relative;
    top: 40%;
    text-align: center;
  }

  .mui-grid-view.mui-grid-9 {
    background-color: #fff;
  }

  .mui-grid-view.mui-grid-9 .mui-table-view-cell {
    border: none;
  }

  .mui-grid-view.mui-grid-9 img {
    width: 60px;
  }

  .mui-table-view.mui-grid-view .mui-table-view-cell .mui-media-body {
    font-size: 14px;
  }
</style>