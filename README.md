<template>
	<div id="app">
		<span v-if="isUser">
			<label for="username">用户账号</label>	
			<input type="text" id="username" placeholder="用户账号" key="username"/>
		</span>
		<span v-else>
			<label for="email">用户邮箱</label>	
			<input type="text" id="email" placeholder="用户邮箱" key="email"/>
		</span>
		<button @click="isUser = !isUser">切换类型</button>
	</div>
	<!--v-show-->
	<!--
    	v-if:当我条件为false时，包含v-if指令 的元素，根本就不会存在dom中
    	v-show：当条件为false时，v-show只是给我们的元素添加一个行内样式:display:none
    	开发中如何选择呢？
    		当需要在显示与隐藏之间切换很频繁时，我们需要使用v-show
    		当只有一次切换时，通过使用v-if
    -->
	<h2 v-if="isShow" id="aaaa">{{message}}</h2>
	<h2 v-show="isShow" id="bbbb">{{message}}</h2>
	<!--
    	for循环遍历数组
   -->		
	<!--在遍历的过程中，没有使用索引值（下标值）-->
	<ul>
		<li v-for="item in names">{{item}}</li>
	</ul>
	<!--在遍历的过程中，获取索引值-->
	<ul>
		<li v-for="(item,index) in names">{{index+1}}.{{item}}</li>
	</ul>
	<!--
    	for循环遍历对象
   -->	
   <ul>
   	<!--1 ，在遍历对象的过程中，如果只是获取一个值，那么获取到的是value-->
   	<li v-for="item in info"></li>
   </ul>
   <ul>
   	<!--2 ，获取key和vaule 格式：（vaule,key）>-->
   	<li v-for="(value,key) in info">{{value}}--{{key}}</li>
   </ul>
   
    <ul>
   	<!-- ，获取key和vaule和index  格式：（vaule,key index）>-->
   	<li v-for="(value,key,index) in info">{{value}}--{{key}}--{{index}}</li>
   </ul>
   
    <ul>
   	<!-- ，获取key和vaule和index  格式：（vaule,key index）>-->
   	<li v-for="item in names" :key="item">{{item}}</li>
   </ul>
</template>
<!--vue内部有些元素复用的问题-->
<script>
	const app  = new Vue({
		el:'#app',
		data:{
			message:'122333',
			isShow:true,
			names:['shy','kobe','james','curry'],
			info:{
				name:"why",
				age:18,
				height:1.888
			}
		}
	})
</script>

<style>
</style>
