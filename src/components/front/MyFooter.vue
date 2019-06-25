<template>
  	<div class="footer">
   	  	
		<ul>
			
			<li>Created by chenchen, Powered by Vue<router-link to="/login" tag="span">后台登录</router-link></li>
		</ul>	 
 	</div>
</template>

<script>
import util from '../../util.js'
export default {
	

}
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
.footer{
	  width:100%;
	  overflow: hidden;
	  display: block;
	  position: relative;
	  margin-top: 30px;
	  height:200px;
	  z-index: 6;
	  #foot-bg{		
			position: absolute;
			left: 0px;
			bottom: 0px;
	  }
	  ul{		
		position: relative;
		top: 50%;
		transform: translateY(0, -50%);
		color: #999;
		li{
			margin-top: 10px;
			span{
				border-left: 1px solid #999;
				margin-left: 20px;
				padding-left: 5px;
				color:#808ccc;
				cursor:pointer;
				font-weight: bold;

			}
			span:hover{
				
			}
	    }
	  } 
}
@media screen and (max-width: 450px){
	.footer{
	  font-size: 12px;
	}
	
} 


</style>
