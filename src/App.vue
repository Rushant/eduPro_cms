<template>
  <div id="app">
    <div class="sidebar">
      <ul class="dropdown">
        <li v-for="menu in menus" :class="{active: true}" v-on:click="changePage(menu)">
        <router-link ></router-link>
          {{menu.name}}
        </li>
      </ul>
    </div>
    <router-view></router-view>
  </div>
</template>
<script>
export default {
  name: 'app',
  data() {
    return {
      menus: [{
        name: '用户管理',
        icon: '',
        path: '',
        submenu: '',
      }, {
        name: '信息管理',
        icon: '',
        path: '',
        submenu: '',
      },{
        name: '课程管理',
        icon: '',
        path: '',
        submenu: '',
      },{
        name: '教师管理',
        icon: '',
        path: '',
        submenu: '',
      },{
        name: '学生管理',
        icon: '',
        path: '',
        submenu: '',
      }]
    }
  },
  methods: {
  changePage: function(page){
    console.log(page.name);
  }
  }
}

</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.sidebar {
  transition: all 0.5s;
  width: 400px;
  overflow: hidden;
}

.dropdown {
  background-color: #e78170;
}

</style>
