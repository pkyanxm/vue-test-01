<template>
	<div>
		<div style="margin-bottom: 20px;">
		  <el-button @click="change()">切换</el-button>
		</div>
		<el-menu :default-openeds="['1']" class="el-menu-vertical-demo" :collapse="isCollapse">
	      <el-submenu index="1">
	        <template slot="title"><i class="el-icon-message"></i><span slot="title">导航一</span></template>
	        <el-menu-item-group>
		          <template slot="title"><i class="el-icon-phone"></i>分组一</template>
		          <el-menu-item index="1-1">选项1</el-menu-item>
		          <el-menu-item index="1-2">选项2</el-menu-item>
	        </el-menu-item-group>
	      </el-submenu>
	      <el-submenu index="2">
	        <template slot="title"><i class="el-icon-menu"></i><span slot="title">导航2</span></template>
	        <el-submenu index="2-1">
	          <template slot="title">选项1</template>
	          <el-menu-item index="2-1-1">选项1-1</el-menu-item>
	        </el-submenu>
	      </el-submenu>
	      <el-submenu index="3">
	        <template slot="title"><i class="el-icon-setting"></i><span slot="title">导航3</span></template>
	        <el-menu-item-group>
	          <template slot="title">分组一</template>
	          <el-menu-item index="3-1">选项1</el-menu-item>
	          <el-menu-item index="3-2">选项2</el-menu-item>
	        </el-menu-item-group>
	      </el-submenu>
	    </el-menu>
	  </el-aside>
	</div>
</template>

<script type="text/javascript">
	export default {
		name: '',
		data() {
			return {
				isCollapse: false
			}
		},
		methods: {
			 change() {
			 	console.log(this.isCollapse);
			 	this.isCollapse = !this.isCollapse;
			 	
		      },
		      handleOpen(key, keyPath) {
		        console.log(key, keyPath);
		      },
		      handleClose(key, keyPath) {
		        console.log(key, keyPath);
		      }
		}
	}
</script>

<style type="text/css">
	.el-menu-vertical-demo:not(.el-menu--collapse) {
	    width: 200px;
	    min-height: 400px;
	  }
</style>