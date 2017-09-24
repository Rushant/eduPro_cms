<template>
  <div class="login">
    <h1>{{ msg }}</h1>
    <input v-model="username" palceholder="用户名">
    <input v-model="password" palceholder="密码">
    <button v-on:click="login">登录</button>
  </div>
</template>
<script>
export default {
  name: 'login',
  data() {
    return {
      msg: '学之有道后台管理系统',
      username: '',
      password: '',
      loginUrl: 'static/data/login/login.json'
    }
  },
  methods: {
    login: function(event) {
      //console.log(this.username + this.password)
      this.$http.get(this.loginUrl).then((response) => {
        var result = response.body.msg
        console.log(result)
        this.$router.push({name: 'home'})
      }, (response) => {
        console.log('error')
      })
    }
  }
}

</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

</style>
