<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">主页</router-link>|
      <router-link to="/login">登录</router-link>
      <template v-for="(menu, index) of $store.state.userInfo.menus">
        |<router-link :to="{ name: menu.name }" :key="index">{{menu.title}}</router-link>
      </template>
    </div>
    <router-view/>
  </div>
</template>

<style lang="less">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
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
