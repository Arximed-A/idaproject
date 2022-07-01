<template>
	<header class="header">
		<h2 class="title">
			Добавление товара
		</h2>
		<button class="button">
			По умолчанию
		</button>
	</header>
</template>

<script>
export default {
	name: 'Header',
}
</script>

<style lang="scss" scoped>




.header{
	display: flex;
	justify-content: space-between;
	min-height: 36px;
	margin: 0px 0px 16px 0px;
	
}
.title{
	font-weight: 600;
	font-size: 28px;
	margin: 0px 20px 0px 0px;
	line-height: 35px;
}
@media (max-width: 500px){
	.title{
		font-size: 20px;
		
	}
}
.button{
	border: none;
	color: #B4B4B4;
	border-radius: 4px;
	flex: 0 0 121.49px;
	font-size: 12px;
	display: flex;
	align-items: center;
	justify-content: center;
	box-shadow: 0px 2px 5px 0px rgba(0, 0, 0, 0.1);
	background-color: rgba(255, 254, 251, 1);
	transition:box-shadow 0.3s ease 0s;
	cursor: url('../assets/icon/cursor.svg') 0 0, pointer;
	&::after{
		content: '';
		display: block;
		transform: rotate(45deg);
		height: 4.59px;
		width: 4.59px;
		border-bottom: 1px #B4B4B4 solid;
		border-right: 1px #B4B4B4 solid;
		margin: -2px 0px 0px 5px;
	}
	&:hover{
		box-shadow: 0px 2px 5px 0px rgba(0, 0, 0, 0.8);
	}
}
</style>