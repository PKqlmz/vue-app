<template>
    <div> 
        <div class="div">
        {{msq + '---------' +  id}} 
        </div>
        </div>
</template>
<script>
export default {
    data(){
        return {
            msq : '能和心爱的人一起睡觉，是件幸福的事情；可是，打呼噜怎么办',
            id : this.$route.params.id          //获取id
        }
    }
}
</script>
<style>
.div {
    margin: 20px 40px;
    color: #226eff;
}
</style>
