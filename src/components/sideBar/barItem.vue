<template>
	<div class="container">
		<div class="wrapper">
			<label :for='id' 
				class="label" 
				v-bind:class="{label_dott: type}">
					{{title}}
				<!-- <span class="text-error">Поле является обязательным</span> -->
			</label>
		</div>
		<input v-if="type" 
			:id='id'
			type="text" 
			:placeholder='text'
			 class="input">
		<textarea
			v-else 
			:name='id' 
			:id='id' 
			cols="30" 
			rows="10" 
			class="input input_big" 
			:placeholder='text'>
		</textarea>
	</div>
</template>

<script>
export default {
	name:'BarItem',
	props:{
		title:{
			type: String,
		},
		text: {
			type: String,
		},
		id: {
			type: String,
		},
		type: {
			type: Number,
		},
	},
}
</script>

<style lang="scss" scoped>
.container{
	margin: 0px 0px 10px 0px;
}
.wrapper{
	margin: 0px 0px 4px 0px;
}
.input{
	width: 284px;
	height: 36px;
	font-size: 12px;
	border-radius: 4px;
	border: none;
	padding: 0px 16px ;
	box-shadow: 0px 2px 5px 0px rgba(0, 0, 0, 0.1);
	transition: all 0.3s ease 0s;
	outline-color: rgb(129, 129, 129);
	&:hover{
		box-shadow: 0px 2px 5px 0px rgba(0, 0, 0, 0.4);
	}
	&::placeholder{
		color: rgba(180, 180, 180, 1);
	}
	&_big{
		height: 108px;
		padding: 10px 16px;
		resize:none;
		margin: 0px 0px -5px 0px;
	}
}
// .error {
// 	outline-color: rgba(255, 132, 132, 1);
// }
.label{
	font-size: 10px;
	color: rgba(73, 72, 94, 1);
	position: relative;
	line-height: 13px;
	letter-spacing: -0.2px;
	&_dott{
		&::after{
		content: '';
		display: block;
		height: 4px;
		width: 4px;
		background-color:rgba(255, 132, 132, 1);
		border-radius: 50%;
		position: absolute;
		right: -4px;
		top: 0;
		}
	}
}
.text-error{
	position:absolute;
	width: 100px;
	font-size: 8px;
	color: rgba(255, 132, 132, 1);
	letter-spacing: -0.5px;
}
@media (max-width: 760px){
	.input{
		width: 100%;
	}
}
</style>