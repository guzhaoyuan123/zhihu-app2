<template>
	<div>
		<div class="nav gutter">
			<div class="nav-bar">
				<img id="logo" src="../../public/img/new_logo.ede2316d.png" />
				<ul class="nav-list flex-left">
					<li class="nav-item">
						<router-link class="router" to="/home">首页</router-link>
					</li>
					<li class="nav-item">
						<router-link class="router" to="/explore">发现</router-link>
					</li>
					<li class="nav-item">
						<router-link class="router" to="/question/waiting">等你来答</router-link>
					</li>
					<li class="nav-item abs-center-right">
						<router-link class="router" to="/login">登录</router-link>
					</li>
				</ul>
			</div>
		</div>
		
		 <router-view class="container"/>
	</div>
	<!-- 二级路由入口 -->
	
</template>

<script>
	export default {
		name: 'nav',
		data() {
			return {};
		},
		created() {}
	};
</script>

<style lang="scss" scoped>
	
	.router{
		width: 150px;
		color: white;
		text-decoration: none;
	}
	
	.router-link-active {
		border-bottom: 2px solid #fff;
	}
	
	.nav-bar{
		height: 60px;
		background: linear-gradient(#086DD3,#055DB6);
		position: relative;
		#logo{
			height: 25px;
			width: 60px;
			position: absolute;
			left:30px;
			top:18px;
		}
	}

	.gutter {
		position: relative;
		margin-bottom: 10px;
	}
	.nav-list{
		height: 60px;
		width: 100%;
		background-color: linear-gradient(#086DD3,#055DB6);
		list-style: none;
	}
	
	.nav-item{
		list-style: none;
		float: left;
		width: 150px;
		background-color: linear-gradient(#086DD3,#055DB6);
		font-size: 20px;
		text-align: center;
		line-height: 60px;
		box-sizing: border-box;
	}
	
	li:nth-child(1){
			margin-left: 50px;
	}
	li:nth-child(4){
			margin-left: 600px;
	}
</style>
