<template>
	<div class="find">
		<div class="infoBox1">
			<div class="info1" v-for="(item, index) in dataList" :key="index">
				<div class="content1">
					<img :src="item.banner" />
					<div class="zishubox">
						<h3 class="title">{{ item.title }}</h3>
						<span class="time">{{ item.updated }}</span>
						<h5 class="nierong">{{ item.introduction }}</h5>
					</div>
				</div>
			</div>
		</div>

		<div class="more">
			<h1><router-link  to="special/all">查看更多</router-link></h1>
		</div>
		
		<div class="yuanzoutaolun">
			<img class="tupanyuan" src="../assets/image/yuanzuo.png" />
		</div>
		
		<div class="more2">
			<h1><router-link  to="roundtable">查看更多专题</router-link></h1>
			</div>
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


.infoBox1{
	box-sizing: border-box;
}

.info1{
	display: inline-block;
	margin: 50px;
	width: 600px;
	height: 400px;
	border: 1px solid gray;
}

	
.content1{
	float: left;
}


.more{
	text-align: center;
	margin: 0 auto;
	line-height: 40px;
	border-radius: 20px;
	width: 150px;
	height: 50px;
	background-color: #FFFFFF;
}

.more2{
	text-align: center;
	margin: 0 auto;
	line-height: 40px;
	border-radius: 20px;
	width: 150px;
	height: 50px;
	background-color: #FFFFFF;
}
.time{
	margin-top: 10px;
}
.nierong{
	margin-top: 10px;
}
h1{
	font-size: 18px;
}

.tupanyuan{
	margin: 0 auto;
	display: block;
	width: 1200px;
	height: 500px;
}
</style>
