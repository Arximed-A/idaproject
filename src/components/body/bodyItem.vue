<template>
	<article class="container" :id="id">
		<img :src="img" alt="camera"
			class="img">
		<div class="wrapper">
			<h3 class="title">{{name}}</h3>
			<p class="text">{{text}}</p>
		</div>
			<div class="coast">{{coast}} руб.</div>
	</article>

</template>

<script>
export default {
	name: 'BodyItem',
	props:{
		name:{
			type: String,
		},
		text: {
			type: String,
		},
		coast: {
			type: Number,
		},
		img:{
			type: String
		},
		id:{
			type: Number
		},
	}
}
</script>

<style lang="scss" scoped>





.container{
	min-height: 423px;
	flex: 0 0 332px;
	margin: 0px 0px 16px 16px;
	border-radius: 4px;
	position: relative;
	box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
	cursor: url('../../assets/icon/cursor.svg') 0 0, pointer;
	transition: box-shadow 0.3s ease 0s;
	&::after{
		content: '';
		display: none;
		height: 32px;
		width: 32px;
		background: center no-repeat url('../../assets/icon/basket.svg') ;
		background-color: rgba(255, 132, 132, 1);
		position: absolute;
		right: -8px;
		top: -8px;
		border-radius: 10px;
	}
	&:hover{
		&::after{
			display: block;
		}
			box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.4);
	}
}
.img{
	width: 332px;
	height: 200px;
	display: block;
}
.text{
	line-height: 20.11px;
	margin: 0px 0px 6px 0px;
}
.title{
	font-size: 20px;
	font-weight: 600;
	margin: 0px 0px 16px 0px;
	
}
.wrapper{
	padding: 14px 16px;
}
.coast{
	font-size: 22px;
	font-weight: 600;
	padding: 14px 16px 0;
	margin: 0px 0px 24px 0px;
	// letter-spacing: -0.2px;
}
@media (max-width: 760px){
	.container{
		flex: 1 1 auto;
		margin: 0px 0px 16px 0px;
	}
	.img{
		margin: 0px auto;
	}
}
@media (max-width: 500px){
	.img{
	width: 100%;
	object-fit: cover;
	}
}
</style>