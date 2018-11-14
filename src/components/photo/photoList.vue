<template>
    <div>
        <div id="slider" class="mui-slider ">
				<div id="sliderSegmentedControl" class="mui-scroll-wrapper mui-slider-indicator mui-segmented-control mui-segmented-control-inverted">
					<div class="mui-scroll">
						 <a :class="['mui-control-item', item.id == 0 ? 'mui-active' : '']" v-for="item in list" :key="item.id" @click="getImage(item.id)">
            {{ item.title }}
          </a>
					</div>
				</div>
			</div>
     <ul class="photo-list">
      <router-link v-for="item in imageList" :key="item.id" :to="'/home/photoinfo/' + item.id" tag="li">
        <img v-lazy="item.src">
      </router-link>
    </ul>

    </div>
</template>
<script>
import mui from "../../lib/mui/js/mui.min.js"

 
export default {
    data(){
        return {
           list : [
               {id:1,title:'家居生活'},
               {id:2,title:'美女明星'},
               {id:3,title:'电影海报'},
               {id:4,title:'搞怪萌宠'},
               {id:5,title:'古典美女'},
               {id:6,title:'英雄联盟'},
           ],
          imageList : [] 
        }
    },
    created(){
        this.getList();
        this.getImage(0);
    },
    mounted(){
    mui('.mui-scroll-wrapper').scroll({
        deceleration: 0.0005 //flick 减速系数，系数越大，滚动速度越慢，滚动距离越小，默认值0.0006
    });
    },
    methods : {
        getList(){
            var qb = {id:0,title:'全部'}
            this.list.unshift(qb)
        },
        getImage(id){   //自己模拟数据
            var image = [   //全部
    {name:0,id:10,src:'http://pic.58pic.com/58pic/13/97/60/55G58PIC2nh_1024.jpg'},
    {name:0,id:11,src:'http://pic14.photophoto.cn/20100101/0036036367904622_b.jpg'},
    {name:0,id:12,src:'http://img.bqatj.com/img/236634ae96b56ceb.jpg'},
    {name:0,id:9,src:'http://photocdn.sohu.com/20150903/mp30469333_1441255251258_1.jpeg'},
    {name:0,id:8,src:'http://pic3.16pic.com/00/55/07/16pic_5507165_b.jpg'},
    //j家居生活
    {name:1,id:13,src:'http://pic.58pic.com/58pic/13/97/60/55G58PIC2nh_1024.jpg'},
    {name:1,id:14,src:'http://img.zcool.cn/community/01099258573ef7a8012060c8fb3a89.jpg@1280w_1l_2o_100sh.png'},
    {name:1,id:15,src:'http://www.jianshe99.com/upload/html/2011/2/10/duqiul465820112101403575266.jpg'},
    //美女明星
    {name:2,id:16,src:'http://pic1.win4000.com/wallpaper/2018-09-21/5ba46599a7b2d.jpg?down'},
    {name:2,id:17,src:'http://pic14.photophoto.cn/20100101/0036036367904622_b.jpg'},
    {name:2,id:18,src:'http://img3.imgtn.bdimg.com/it/u=3397713603,3611279759&fm=214&gp=0.jpg'},
    //电影海报
     {name:3,id:19,src:'http://img.bqatj.com/img/236634ae96b56ceb.jpg'},
    {name:3,id:20,src:'http://b-ssl.duitang.com/uploads/item/201601/25/20160125190518_UZCk8.jpeg'},
    {name:3,id:21,src:'http://www.wenzhousx.com/yujeu/wenzhou/1305/4-130522111A7.jpg'},
    //搞怪萌宠
     {name:4,id:22,src:'http://photocdn.sohu.com/20150903/mp30469333_1441255251258_1.jpeg'},
    {name:4,id:23,src:'http://img.keaiq.com/d/file/15245390985659956.jpg'},
    {name:4,id:24,src:'http://www.mengchongzu.com/uploads/allimg/20150223/1424630592524987.jpg'},
    //古典美女
    {name:5,id:25,src:'http://p3.pstatp.com/origin/39ab00006ad5708da777'},
    {name:5,id:26,src:'http://pic1.win4000.com/wallpaper/2018-03-28/5abb2f9584f17.jpg'},
    {name:5,id:27,src:'http://image2.xyzs.com/upload/07/df/279140/20140218/139269406078347_0.jpg'},
    //英雄联盟
    {name:6,id:28,src:'http://pic3.16pic.com/00/55/07/16pic_5507165_b.jpg'},
    {name:6,id:29,src:'http://photo.16pic.com/00/55/07/16pic_5507082_b.jpg'},
    {name:6,id:30,src:'http://pic1.16pic.com/00/39/88/16pic_3988584_b.jpg'}
]
 this.imageList = []
  for(i=0;i<image.length;i++){
     
     if(image[i].name === id){
         this.imageList.push(image[i])
     }
  }
        }
    }
}
</script>
<style scoped>
 * {
     touch-action: pan-y;
 }
 .photo-list {
     padding: 10px;
     margin:0 ;
 }
.photo-list li {
     list-style: none;
     margin-top: 5px;
     background-color: #ccc;
     text-align: center;
   vertical-align: middle;
   box-shadow: 0 0 9px #999;
 }
  .photo-list li img {
      width: 400px;
      height: 230px;
   
  }
  .photo-list img[lazy="loading"] {
      width: 40px;
      height: 300px;
      margin: auto;
    }

</style>

