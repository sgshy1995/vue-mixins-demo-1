<template>
  <div id="app" :class="'theme'+'-'+bg">
    <img v-y width="25%" src="./assets/logo.png">
    <ChangeButton/>
  </div>
</template>

<script>
import log from './mixins/log'
import ChangeButton from './components/ChangeButton'
export default {
  name: "App",
  data(){
    return{
      bg: 'pink'
    }
  },
  components:{ChangeButton},
  mixins: [log],
  directives:{
    y:{
      inserted(el){
        el.addEventListener('click',()=>{
          console.log('y')
        })
      }
    }
  },
  methods:{
    changeTheme(){
      if(this.bg==='pink'){
        this.bg ='orange'
      }else{
        this.bg ='pink'
      }
    }
  },
  provide(){
    return {
      changeTheme:this.changeTheme
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app.theme-pink{
  background: pink;
}
#app.theme-orange{
  background: orange;
}
</style>
