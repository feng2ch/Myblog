<template>
	<div class="wrapper">
		<search></search>
		<my-header></my-header>
		<router-view></router-view>
		<my-footer></my-footer>
	</div>
</template>

<script>
import MyHeader from './MyHeader.vue'
import MyFooter from './MyFooter.vue'
import Search from './../common/Search.vue'

export default {
  	components: {
      MyHeader,
	  MyFooter,
	  Search
  	}
  }
</script>
<style type="stylesheet/scss" scoped>
.wrapper{
	width: 100%;
	position: relative;
	
}
</style>
