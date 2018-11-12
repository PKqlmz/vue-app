<template>
    <div>
        <div id="slider" class="mui-slider ">
				<div id="sliderSegmentedControl" class="mui-scroll-wrapper mui-slider-indicator mui-segmented-control mui-segmented-control-inverted">
					<div class="mui-scroll">
						 <a :class="['mui-control-item', item.id == 0 ? 'mui-active' : '']" v-for="item in list" :key="item.id">
            {{ item.title }}
          </a>
					</div>
				</div>

			</div>
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
           ]
        }
    },
    created(){
        this.getList();
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
        }
    }
}
</script>
<style>
 * {
     touch-action: pan-y;
 }
</style>
