<template>
	<div class="find">
		<div class="infoBox1">
			<div class="info1" v-for="(item, index) in dataList" :key="index">
				<div class="content1">
					<img :src="item.banner" class="find_img" />
					<div class="zishubox">
						<h3 class="find_title">{{ item.title }}</h3>
						<span class="find_time">{{ item.updated }}</span>
						<h5 class="find_nierong">{{ item.introduction }}</h5>
					</div>
				</div>
			</div>
		</div>

		<div class="more">
			<h1 class="find_h1">
				<router-link to="special/all">查看更多</router-link>
			</h1>
		</div>

		<div class="yuanzoutaolun">
			<img class="tupanyuan" src="../assets/image/yuanzuo.png" />
		</div>

		<div class="more2">
			<h1 class="find_h1">
			<router-link class="explore-more" to="roundtable">查看更多专题</router-link>
			</h1>
		</div>
		<div class="explore-box"></div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				dataList: []
			};
		},
		created() {
			this.getData();
		},
		methods: {
			getData() {
				this.axios.get('http://localhost:8888/api/special/').then(res => {
					this.dataList = res.data.data;
				});
			}
		}
	};
</script>

<style>
	.find {
		width: 100%;
	}

	.infoBox1 {
		margin: 0 auto;
		width: 1360px;
	}

	.info1 {

		display: inline-block;
		margin-left: 55px;
		margin-top: 20px;
		width: 600px;
		height: 400px;
		border-radius: 5px;
		border: 1px solid gainsboro;
		background: white;
	}

	.find_img {
		width: 600px;
		height: 250px;
	}


	.content1 {
		float: left;
	}


	.more {
		text-align: center;
		margin: 0 auto;
		line-height: 40px;
		border-radius: 20px;
		width: 150px;
		height: 50px;
		background-color: #FFFFFF;
	}

	.more2 {
		text-align: center;
		margin: 0 auto;
		line-height: 40px;
		border-radius: 20px;
		width: 150px;
		height: 50px;
		background-color: #FFFFFF;
	}

	.find_time {
		margin-top: 10px;
		padding-left: 30px;
	}

	.find_nierong {
		margin-top: 10px;
		width: 90%;
		padding-left: 30px;
	}
	
	.find_title{
		padding-left: 30px;
	}
	.find_h1{
		margin-top: 30px;
	}
	
	.find_h1 a{
		font-size: 18px;
		text-decoration: none;
	}

	.tupanyuan {
		margin: 0 auto;
		display: block;
		width: 1250px;
		height: 600px;
	}
	
	.explore-more{
		font-size: 18px;
		text-decoration: none;
	}
	
	.explore-box{
		height: 50px;
		width: 100%;
	}
</style>
