<template>
    <div> 
        <div class="div">
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        {{msq + '---------' +  id}} 
        </div>
        <comment-box></comment-box>
        </div>
</template>
<script>
import Comment from '../subcomponents/comment.vue'
export default {
    data(){
        return {
            msq : '能和心爱的人一起睡觉，是件幸福的事情；可是，打呼噜怎么办',   //没有数据接口。所以自己模拟
            id : this.$route.params.id          //获取id
        }
    },
    components :  {
        'comment-box' : Comment
    }
}
</script>
<style>
.div {
    margin: 20px 40px;
    color: #226eff;
}
</style>
