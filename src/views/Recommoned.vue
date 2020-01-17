<template>
	<div class="tuijian"><h3>推荐</h3></div>
	
</template>

<!-- // http://localhost:8888/api/special/ -->
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
		
		}
	}
};
</script>

<style lang="scss" scoped>
.tuijian {
	margin-left: 150px;
	margin-top: -20px;
	width: 1000px;
	height: 1000px;
	background-color: white;
}
h3 {
	font-size: 30px;
}
</style>
