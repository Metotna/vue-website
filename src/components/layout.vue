<template>
	<div id="layout">
		<header>
			<img src="../assets/logo.png" height="70" >
			<ul><li>登录</li> | <li>注册</li> | <li>关于</li></ul>
		</header>
		<content>
			<router-view></router-view>
		</content>
        
		<footer>这是尾部</footer>
	</div>
</template>
<script >
	export default {
		name:'layout'
	}
</script>
<style>
	@import '../css/reset.css';
	html{
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
	}
	header{
		background-color: #fff;
		height: 70px;
		padding: 10px  50px;
		background-color: #50616b;
	}
	header ul {
		float: right;
		line-height: 70px;
		color: #fff;
	}
	header ul li {

		display: inline-block;
	}
	footer{
		text-align: center;
		line-height: 70px;
		height: 70px;
		padding: 10px  50px;
		background-color: #fff;
	}
	content{
		background-color: #f0f0f0;
		padding:20px 50px;
		display: block;

	}
</style>