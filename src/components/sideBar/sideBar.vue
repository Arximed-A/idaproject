<template>
  <aside class="wrapper">
    <form action="#" class="form" method="post" id="form">
      <BarItem 
        :title="'Наименование товара'" 
        :goal="'Введите наименование товара'" 
        :id="'name'" 
        :size="1"
        :type="'text'" 
      />
      <BarItem 
        :title="'Описание товара'"
        :goal="'Введите описание товара'" 
        :id="'description'" 
        :size="0"
        :type="'text'" 
      />
      <BarItem 
        :title="'Ссылка на изображение товара'" 
        :goal="'Введите ссылку'" 
        :id="'link'" 
        :size="1" 
        :type="'text'" 
      />
      <BarItem 
        :title="'Цена товара'"
        :goal="'Введите цену'" 
        :id="'cost'" 
        :size="1" 
        :type="'number'" 
      />
      <button v-if="!activeButton" class="button" disabled >
        Добавить товар
      </button>
      <button v-else class="button button_active" >
        Добавить товар
      </button>
    </form>
  </aside>
</template>

<script>
import BarItem from './barItem.vue';
export default {
  name:'SideBar',
  props:{
    activeButton:{
      type: Boolean,
    }
  },
  components: {
    BarItem,
  },
  data(){
    return{
    }
  },
  methods:{
    changeActiveButton(){
      this.active = !this.active;
    }
  },
  computed:{

  }
}
</script>

<style lang="scss" scoped>
.button{
  margin: 11px 0px 0px 0px;
  height: 36px;
  border: none;
  color: rgba(180, 180, 180, 1);
  font-weight: 600;
  border-radius: 10px;
  background-color: rgba(238, 238, 238, 1);
  transition: all 0.3s ease 0s;
  font-size: 13px;
  &_active{
    background: rgba(123, 174, 115, 1);
    color: #FFFFFF;
    cursor: url('../../assets/icon/cursor.svg') 0 0, pointer;
  }
}
  .wrapper{
    flex: 0 1 332px;
    background: #FFFEFB;
    margin: 0px 0px 20px 0px;
  }
@media (max-width: 760px){
  .wrapper{
    flex: 1 1 auto;
  }
}
  .form{
    display: flex;
    flex-direction: column;
    padding: 16px 24px;
    box-shadow: 0px 6px 10px 0px rgba(0, 0, 0, 0.02), 0px 20px 30px 0px rgba(0, 0, 0, 0.04);
  }
</style>