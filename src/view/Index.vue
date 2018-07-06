<template>
	<el-container style="border: 1px solid #eee">
		  <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
		  		<left></left>
		  </el-aside>
		  <el-container>
		    	<el-header>
		    		<header-top></header-top>
		    	</el-header>
		    	<el-main>
		    		<main-list></main-list>
		    	</el-main>
		  </el-container>
	</el-container>
</template>

<script type="text/javascript">
	import Left from './Left'
	import MainList from './Main'
	import HeaderTop from './Header'

	export default{
		data() {
			return {
				
			}
		},
		methods: {
			
		},
		components: {
			Left,
			MainList,
			HeaderTop
		}
	}
</script>

<style type="text/css">
	.el-header, .el-footer {
	    background-color: #B3C0D1;
	    color: #333;
	    text-align: center;
	    line-height: 60px;
	 }
	  
	  .el-main {
	    background-color: #E9EEF3;
	    color: #333;
	    text-align: center;
	    line-height: 160px;
	  }
	  
	  body > .el-container {
	    margin-bottom: 40px;
	  }
	  
	  .el-container:nth-child(5) .el-aside,
	  .el-container:nth-child(6) .el-aside {
	    line-height: 260px;
	  }
	  
	  .el-container:nth-child(7) .el-aside {
	    line-height: 320px;
	  }
</style>