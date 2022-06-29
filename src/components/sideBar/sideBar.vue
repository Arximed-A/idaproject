<template>
	<aside class="wrapper">
		<form action="#" class="form">
			<BarItem 
				:title="'Наименование товара'" 
				:text="'Введите наименование товара'" 
				:id="'name'" 
				:type="1" />
			<BarItem 
				:title="'Описание товара'"
				:text="'Введите описание товара'" 
				:id="'description'" 
				:type="0" />
			<BarItem 
				:title="'Ссылка на изображение товара'" 
				:text="'Введите ссылку'" 
				:id="'link'" 
				:type="1" />
			<BarItem 
				:title="'Цена товара'"
				:text="'Введите цену'" 
				:id="'cost'" 
				:type="1" />
			<button class="button">
				Добавить товар
			</button>
		</form>
	</aside>
</template>

<script>
import BarItem from './barItem.vue';
export default {
	name:'SideBar',
	components: {
		BarItem,
	}
}
</script>

<style lang="scss" scoped>


.button{
	margin: 8px 0px 0px 0px;
	height: 36px;
	border: none;
	color: rgba(180, 180, 180, 1);
	font-weight: 600;
	border-radius: 10px;
	background-color: rgba(238, 238, 238, 1);
}
	.wrapper{
			flex: 0 1 332px;
			min-height: 440px;
			box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
	}
	.form{
			display: flex;
			flex-direction: column;
			padding: 24px 24px 0;
	}
</style>