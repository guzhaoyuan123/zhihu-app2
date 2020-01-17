<template>
	<div class="round">
		<div class="round_info">
			<div class="info_v" v-for="(item, index) in dataList" :key="index">
				<div class="round_content">
					<div class="round_box2"><img :src="item.banner" class="round_img" /></div>
					<div class="round_box3">
						<h3 class="round_name">{{ item.name }}</h3>
						<span class="round_visitsCount">该圆桌被浏览&nbsp;{{ item.visitsCount }} 次</span>
					</div>
				</div>
			</div>
		</div>
		<div class="round_cebian">
			<img src="../assets/image/cebian.png" />
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
			this.axios.get('http://localhost:8888/api/roundtable/').then(res => {
				this.dataList = res.data.data;
			});
		}
	}
};
</script>

<style>

.round_cebian{
	margin-top: 20px;
	border-radius: 5px;
	width: 280px;
	background-color: #000000;
}
.round_info {
	float: left;
	margin-left: 200px;
	display: inline-block;
	width: 800px;
}
.info_v {
	margin: 20px;
	float: left;
	background-color: white;
	position: relative;
	width: 200px;
	height: 240px;
	border-radius: 5px;
	border: 1px solid gainsboro;
}

.round_img {
	width: 200px;
	height: 200px;
}
.round_name {
	position: absolute;
	top: 140px;
	left: 5px;
	right: 5px;
	font-size: 16px;
	font-weight: 200;
	color: white;
}

span {
	display: block;
	margin-left: 10px;
	margin-top: 5px;
	color: gray;
	font-size: 14px;
}
</style>
