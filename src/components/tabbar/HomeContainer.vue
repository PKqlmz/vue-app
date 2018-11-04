<template>
  <div>
    
    <!-- 轮播图区域 -->
    <mt-swipe :auto="4000">
      <!-- 在组件中，使用v-for循环的话，一定要使用 key -->
      <mt-swipe-item v-for="item in lunbotuList" :key="item.id">
        <img :src="item.img" alt="">
      </mt-swipe-item>
    </mt-swipe>

     <!-- 九宫格 到 6宫格 的改造工程 -->
    <ul class="mui-table-view mui-grid-view mui-grid-9">
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><a href="#">
              <img src="../../images/menu1.png" alt="">
              <div class="mui-media-body">新闻资讯</div></a></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><a href="#">
              <img src="../../images/menu2.png" alt="">
              <div class="mui-media-body">图片分享</div></a></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><a href="#">
              <img src="../../images/menu3.png" alt="">
              <div class="mui-media-body">商品购买</div></a></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><a href="#">
              <img src="../../images/menu4.png" alt="">
              <div class="mui-media-body">留言反馈</div></a></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><a href="#">
              <img src="../../images/menu5.png" alt="">
              <div class="mui-media-body">视频专区</div></a></li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><a href="#">
              <img src="../../images/menu6.png" alt="">
              <div class="mui-media-body">联系我们</div></a></li>
  </ul> 

    
   
  </div>
</template>

<script>
// import { Toast } from "mint-ui";  toast组件暂时用不到

export default {
  data() {
    return {
      lunbotuList: [
       { id :1,img : "http://pic29.nipic.com/20130511/9252150_174018365301_2.jpg"},
       {id: 2, img : "http://pic19.nipic.com/20120210/7827303_221233267358_2.jpg"},
      { id : 3,img : "http://pic29.nipic.com/20130511/9252150_174018365301_2.jpg"}
      ] // 保存轮播图的数组
    };
  },
  created() {
    // this.getLunbotu();
  },
  methods: {
    // getLunbotu() {
    //   // 获取轮播图数据的方法(get后的地址为接口，因为不能用，所以模拟了一下)
    //   this.$http.get("http://vue.studyit.io/api/getlunbo").then(result => {
    //     // console.log(result.body);
    //     if (result.body.status === 0) {
    //       // 成功了
    //       this.lunbotuList = result.body.message;
    //     } else {
    //       // 失败的
    //       Toast("加载轮播图失败。。。");
    //     }
    //   });
    // }
  }
};
</script>

<style  scoped>
.mint-swipe {
  height: 200px;
  }

.mint-swipe .mint-swipe-item:nth-child(1) {
      background-color: red;
 }
.mint-swipe .mint-swipe-item:nth-child(1) {
      background-color: red;
 }  
.mint-swipe .mint-swipe-item:nth-child(1) {
      background-color: red;
}
.mint-swipe .mint-swipe-item img {
      width: 100%;
      height: 100%;
}
    
.mui-grid-view.mui-grid-9 {
  background-color: #fff;
  border: none; }

  .mui-grid-view.mui-grid-9 img {
    width: 60px;
    height: 60px;
  }

.mui-grid-view.mui-grid-9  .mui-media-body{
    font-size: 13px;
  }

.mui-grid-view.mui-grid-9 .mui-table-view-cell {
  border: 0;
}  

</style>
