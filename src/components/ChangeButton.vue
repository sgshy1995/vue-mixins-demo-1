<template>
  <div>
    <button @click="x">换肤功能</button>
  </div>
</template>

<script>
export default {
    inject:['changeTheme'],
    methods:{
      x(){
        this.changeTheme()
      }
    }
};
</script>

<style lang="scss" scoped>
</style>