<template>
	<body class="body">
		<BodyItem 
			v-for="item of items"
			:key="item.id"
			:name="item.name" 
			:text="item.text" 
			:coast="item.coast" 
			:img="item.img"
		/>
	</body>
</template>

<script>
import BodyItem from './bodyItem.vue';

export default {
	name: "BodyPage",
	components: {
		BodyItem 
	},
	data(){
		return{
			items: null,
		}
	},
	created(){
		this.items = this.$root.items
	},
}
</script>

<style lang="scss" scoped>
.body{
	display: flex;
	flex-wrap: wrap;
}
</style>