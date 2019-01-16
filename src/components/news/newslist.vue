<template>
  <div>
    <ul class="mui-table-view">
      <li class="mui-table-view-cell mui-media" v-for="item in data">  
        <a href="javascript:;">
          <img class="mui-media-object mui-pull-left" src="http://img3.imgtn.bdimg.com/it/u=2871916202,273723619&fm=11&gp=0.jpg">
          <div class="mui-media-body">
            {{item.title}}
            <p class='mui-ellipsis'>{{item.content}}</p>
          </div>
        </a>
      </li>


    </ul>
  </div>
</template>

<script>
  const Mock = require('mockjs')
  export default {
    data() {
      return {
        title: '1',
        content: '2',
        data: []
      }
    },
    created() {

      var mockObj = Mock.mock('http://www.hehe.com', {
        'title|1-10': 25,//生成一个大于等于 20、小于等于 30 的整数，属性值 25 只是用来确定类型
        'content|11-20': 25
      })

      this.$axios.get('http://www.hehe.com')
        .then((response) => {
          this.data.push(response.data)
          this.data.push(response.data)
          this.data.push(response.data)
        })
        .catch((error) => {
          console.log(error)
        })
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>