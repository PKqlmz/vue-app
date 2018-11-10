<template>
    <ul class="mui-table-view">
				<li class="mui-table-view-cell mui-media">
					<router-link :to="'/home/newsIfo/' +1">
						<img class="mui-media-object mui-pull-left" src="http://pic29.nipic.com/20130511/9252150_174018365301_2.jpg">
						<div class="mui-media-body">
							<h1>能和心爱的人一起睡觉，是件幸福的事情；</h1>
							<p class='mui-ellipsis'>
                                <span>发表时间：2018年11月10日</span>
                                <span>点击次数：5</span>
                            </p>
						</div>
					</router-link>
				</li>
				
			</ul>
</template>
<script>

</script>
<style>
.mui-table-view li h1{
font-size: 14px;
color : #226aff
}
.mui-table-view li .mui-media-body .mui-ellipsis {
display: flex;
justify-content: space-between;
}
</style>
