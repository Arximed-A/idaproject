<template>
	<div class="container">
		<div class="wrapper">
			<label :for='id' class="label" v-bind:class="{label_dott: type}">
				{{title}}
			</label>
		</div>
		<input v-if="type" :id='id' type="text" :placeholder='text' class="input">
		<textarea v-else 
			:name='id' 
			:id='id' 
			cols="30" 
			rows="10" 
			class="input input_big" 
			:placeholder='text'
			></textarea>
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
	margin: 0px 0px 16px 0px;
}
.wrapper{
	margin: 0px 0px 4px 0px;
}
.input{
	width: 284px;
	height: 36px;
	font-size: 12px;
	border-radius: 4px;
	box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
	border: none;
	padding: 0px 16px ;
	&::placeholder{
		color: rgba(180, 180, 180, 1);
	}
	&_big{
		height: 108px;
		padding: 10px 16px;
		resize:none;
	}
}
.label{
	font-size: 10px;
	color: rgba(73, 72, 94, 1);
	position: relative;
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
</style>