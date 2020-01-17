<template>
    <div class="special">
        <div class="infoBox">
            <div class="info" v-for="(item,index) in dataList" :key="index">
                <div class="special_content">
					<div class="special_box1">
						 <img :src="item.banner"/>
					</div>
					<div class="special_box2">
						<h3 class="title">{{item.title}}</h3>
						<span class="time">{{item.updated}}</span>
						<span class="nierong">
						    {{item.introduction }}
						</span>
					</div>
            
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                dataList: [],
            };
        },
        created() {
            this.getData();
        },
        methods: {
            getData() {
                this.axios.get("http://localhost:8888/api/special/all").then(res => {
                    this.dataList = res.data.data;
                })
            }
        }
    };
</script>


<style>
    img{
		margin-top: 20px;
        width: 300px;
        height: 140px;
    }
    .special_content{
		margin: 20px auto;
		border-radius: 5px;
		width: 1000px;
		border: 1px solid #DCDCDC;
		height: 180px;
		background-color: white;
    }
    .find {
        width: 100%;
        height: 100%;
    }
	.special_box1{
		width: 300px;
		height: 140px;
		margin-left: 20px;
		float: left;
	}
	.special_box2{
		margin-top: 20px;
		margin-left: 20px;
		width: 600px;
		float: left;
	}

  .nierong{
	  color: gray;
  }
   
</style>