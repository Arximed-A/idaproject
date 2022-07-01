<template>

<HeaderPage/>
	<main class="main-container">
		<SideBar/>
		<BodyPage />
	</main>

</template>

<script>

import HeaderPage from './components/headerPage.vue';
import SideBar from './components/sideBar/sideBar.vue';
import BodyPage from './components/body/bodyPage.vue';
import data from './data/db.json';
export default {
  name: 'App',
  components: {
    BodyPage,
    SideBar,
    HeaderPage
	},
	data(){
		return{
			items: null,
		}
	},
	created(){
		this.items = data;
	}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;600&display=swap');
#app{
	padding: 32px;
	background-color: rgba(255, 254, 251, 0.8);
}
*{
	font-family: 'Source Sans Pro', sans-serif;
	margin: 0px;
	padding: 0px;
	box-sizing: border-box;
	color: #3F3F3F;
	font-size: 16px;
	font-weight: 400;
}
.main-container{
	display: flex;
	
}
@media (max-width: 760px) {
	.main-container{
		flex-wrap: wrap;
	}
	#app {
		padding: 10px;
	}
}


</style>
