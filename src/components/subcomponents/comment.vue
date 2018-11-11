<template>
 <div  class="cmt-container">
     <h3>发表评论</h3>
     <hr>

    <textarea placeholder="请输入要BB的内容（最多120个字）" maxlength="120" v-model="com"></textarea>
    <mt-button type="primary" size="large" @click="fbpl">发表评论</mt-button>
    <div class="cmt-list" v-for="(item,i) in list" :key="item.cTime">
        <div class="cmt-item">
            <div class="cmt-title">
                第{{i+1}}楼&nbsp;&nbsp;用户：{{item.name}}&nbsp;&nbsp;发表时间：{{item.cTime}}
            </div>
            <div class="cmt-body">
               {{item.cmt}}
            </div>
        </div>
    </div>
     
    <mt-button type="primary" size="large" plain class="button" @click="getMore"> 加载更多</mt-button>
  
    </div>
</template>
<script>
export default {
    data(){
        return {
            list : [
     {
         
        name : '匿名用户',
        cTime : '2018-11-11 11:11:11',
        cmt : ' 哈哈哈哈哈~~~~'
                },
      {
          
        name : '匿名用户',
        cTime : '2018-11-11 11:11:12',
        cmt : ' 哈哈哈哈哈~~~~'
                }, 
      {
          id : 3,
        name : '匿名用户',
        cTime : '2018-11-11 11:11:13',
        cmt : ' 哈哈哈哈哈~~~~'
                },  
            ],
            com : ""
        }
    },
    created(){

    },
    methods : {   //没有数据接口自己模拟
        getMore(){
            var  newList = [
     {
        name : '匿名用户',
        cTime : '2018-11-11 11:11:16',
        cmt : ' 吼吼吼吼~~~~'
                },
      {
        name : '匿名用户',
        cTime : '2018-11-11 11:11:17',
        cmt : ' 红红火火~~~~'
                }, 
      {
        name : '匿名用户',
        cTime : '2018-11-11 11:11:18',
        cmt : ' 恍恍惚惚~~~~'
                },  
            ]
            this.list = this.list.concat( newList)
        },
        fbpl(){
         var dt = new Date()
         var y = dt.getFullYear()        
         var m = (dt.getMonth() + 1).toString().padStart(2,'0')
         var d = ( dt.getDate()).toString().padStart(2,'0')
         var hh = (dt.getHours()).toString().padStart(2,'0')
         var mm = (dt.getMinutes()).toString().padStart(2,'0')
         var ss = (dt.getSeconds()).toString().padStart(2,'0')
         var ctime = `${y}-${m}-${d} ${hh}:${mm}:${ss}`
         var list = {
        name : '匿名用户',
        cTime :ctime,
        cmt : this.com
            }
            this.list.unshift(list)
           
        }
    }
}
</script>

<style>

 .cmt-container h3 {
     font-size: 18px;
 }
.cmt-container textarea {
    font-size: 14px;
   
     height: 75px;
}
.cmt-container .cmt-list {
  margin: 5px 0;
}
.cmt-container .cmt-list .cmt-title {
    font-size: 13px;
    background-color: #ccc;
  
}
.cmt-container .cmt-list .cmt-body {
    line-height: 35px;
     text-indent: 2em;
}
.button {
    margin-bottom: 50px;
}
</style>
