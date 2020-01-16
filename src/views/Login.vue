<template>
	<div class="login-bar" tx-center>
		<router-link to="/">
			<img src="../assets/image/山竹.png" class="logo" />
		</router-link>
	</div>
</template>

<script>
	export default{
		name:'login',
		data() {
			return {};
		},
		created() {}
	};
</script>

<style lang="scss" scoped>
	.login-bar{
		width: 100%;
		height: 800px;
		text-align: center;
		background-color: #f6f6f6;
		
	}
	.logo{
		margin-top: 25px;
		width: 50px;
		height: 50px;
	}
</style>

