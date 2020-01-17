<template>
    <div class="special">
        <div class="infoBox">
            <div class="info" v-for="(item,index) in dataList" :key="index">
                <div class="content">
					<div class="box2">
						 <img :src="item.banner"/>
					</div>
					<div class="box3">
						<h3 class="title">{{item.title}}</h3>
						<br>
						<span class="time">{{item.updated}}</span>
						<h5 class="nierong">
						    {{item.introduction }}
						</h5>
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
        width: 600px;
        height: 250px;
    }
    .content{
		border: 1px solid black;
		height: 300px;
    }
    .find {
        width: 100%;
        height: 100%;
    }
	.box2{
		text-align: center;
		margin-left: 80px;
		float: left;
	}
	.box3{
		margin-left: 80px;
		float: left;
	}

    .picture {
        width: 550px;
        height: 150px;
    }
    .title {
        width: 550px;
    }
    .time {
        width: 550px;
    }
    .nierong {
        width: 550px;
    }
    .box2 {
        text-align: center;
        background-color: aqua;
    }
</style>