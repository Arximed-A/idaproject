<template>
  <div class="container">
    <div class="wrapper">
      label :for='id' class="name" v-bind:class="{name_dott: type}">
        {{title}}
      /label>
    </div>
    <div v-if="type" class="error-wrapper">
      <input :id='id' type="text" :placeholder='text' class="box" v-bind:class="{box_error: error}">
      <span v-if='error' class="text-error">Поле является обязательным</span>
    </div>
    <textarea v-else :name='id' :id='id' cols="30" rows="10" class="box box_big" :placeholder='text'>
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
  data() {
    return {
      error: false,
    }
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
.box{
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
  &_error{
  	// outline-color: rgba(255, 132, 132, 1);
    border: 2px solid rgba(255, 132, 132, 1);
  }
}

.name{
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
.error-wrapper{
  position: relative;
}
.text-error{
  position:absolute;
  width: 100px;
  font-size: 8px;
  color: rgba(255, 132, 132, 1);
  letter-spacing: -0.5px;
  bottom: -14px;
  left:0px;
}
@media (max-width: 760px){
  .box{
    width: 100%;
  }
}
</style>