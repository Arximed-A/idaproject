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

export default {
  name: 'App',
  components: {
    BodyPage,
    SideBar,
    HeaderPage
	}
}
</script>

<style>
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

</style>
