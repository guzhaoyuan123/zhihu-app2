<template>
	<div class="box1"><h3>推荐</h3></div>
</template>

<!-- // http://localhost:8888/api/special/ -->
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
                this.axios.get("http://localhost:8888/api/special/").then(res => {
                    this.dataList = res.data.data;
                })
            }
        }
    };
</script>

<style l ang="scss" scoped>
.box1 {
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
