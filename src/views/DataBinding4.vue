<template>
	<div class="container" v-bind:class="simpleClass">
		Hello
	</div>
	<div class="container" v-bind:class="{ active: activeValue, 'text-red': redValue }">
		Hello
	</div>
	<div class="container" v-bind:class="{ active: activeClass, 'text-red': redClass }">
		Hello
	</div>
	<div style="color: red; background: yellow;">sty1</div>
	<div v-bind:style="{ color: att1, background: att2 }">
		sty2
	</div>
	<div v-bind:style="colorStyle">sty3</div>
</template>

<script>
export default {
	data() {
		return {
			simpleClass: 'active text-red',
			activeValue: true,
			redValue: false,
			activeClass: 'active',
			redClass: 'text-red',
			att1: 'red',
			att2: 'yellow',
			//colorStyle: 'color: red; background: yellow;'
			colorStyle :{
				color:'red',
				background:'yellow'
			}
		};
	},
	//mount는 data 영역 끝나고 선언 해야 함.
	mount(){
		console.log(this);
	},
	method:{
		//이벤트 실행함수
	}
	
};
</script>

<style>
  .container{
    width : 100%;
    height : 50px;
  }
  .active{
    background-color: yellow;
    font-weight: bold;
  }
  .text-red{
    color:red;
  }
</style>