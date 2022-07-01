<template>
  <HeaderPage />
  <main class="main-container">
    <SideBar 
      :activeButton= "activeButton" 
    />
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
      activeButton: false,
      iHaveNoIdea:{
        name: false,
        link: false,
        cost: false,
      }
      
    }
  },
  created(){
    this.items = data;
  },
  methods:{
    checkForm(id, show){
      // не нравится это решение, хотя оно и работает.
      switch(id){
        case 'name': this.iHaveNoIdea.name = show; 
          break;
        case 'link': this.iHaveNoIdea.link = show;
          break;
        default: this.iHaveNoIdea.cost = show;
      }
      const { name, link, cost } = this.iHaveNoIdea;
      if (name && link && cost){
        this.activeButton = true;
      } else{
        this.activeButton = false;
      }
    },
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