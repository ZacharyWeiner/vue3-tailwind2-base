<template>
<div> 
    <menu-dark-base/>
  <Suspense> 
    <template #default >
      <router-view/>
    </template>
    <template #fallback >
      <div class=""> Loading ... </div>
    </template>
  </Suspense>
  </div>
</template>

<script> 
import MenuDarkBase from "./components/tailwind/menus/MenuDarkBase.vue"
export default {
  name: "App", 
  components:{
    MenuDarkBase
  }
}
</script> 

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
