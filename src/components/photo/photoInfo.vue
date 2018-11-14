<template>
    <div>
       <h3> 图片详情</h3>
       <vue-preview :slides="list" @close="handleClose" class="my"></vue-preview>
      <comment-box></comment-box>
    </div>
</template>
 <script>
 import Comment from '../subcomponents/comment.vue'
export default {
    data(){
        return {
            list : [
                {src:'http://pic.58pic.com/58pic/13/97/60/55G58PIC2nh_1024.jpg',msrc:'http://pic.58pic.com/58pic/13/97/60/55G58PIC2nh_1024.jpg',w:600,h:400},
                {src:'http://pic3.16pic.com/00/55/07/16pic_5507165_b.jpg',msrc:'http://pic3.16pic.com/00/55/07/16pic_5507165_b.jpg',w:600,h:400},
                {src:'http://pic1.16pic.com/00/39/88/16pic_3988584_b.jpg',msrc:'http://pic1.16pic.com/00/39/88/16pic_3988584_b.jpg',w:600,h:400}
            ]
        }
    },
    components : {
        'comment-box' : Comment
    },
     methods: {
      handleClose () {
        console.log('close event')
      }
    }
}
 </script>
<style >
.my .my-gallery {
    display: flex;
}
.my figure {
    margin: 5px;
}
 .my a img  {
     width: 100px;
     height: 50px;

 }
</style>
