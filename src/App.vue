<template>
	<div id="app">
		<router-view></router-view>
	</div>
</template>

<script>
	export default {
		name: 'app'
	}
</script>

<style>
	html, body {
		height: 100%;
		width: 100%;
		margin: 0;
		padding: 0;
	}

	#app {
		height: 100%;
		font-family: "Arial","Microsoft YaHei","黑体","宋体",sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		color: #2C3E50;
	}
</style>
<style src="./style/style.css" ></style>
