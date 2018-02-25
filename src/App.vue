<template>
  <div id="app">
    <img src="./assets/logo.png">
    <ul>
      <li><router-link to="/test">Test</router-link></li>
      <li><router-link to="/users">Users</router-link></li>
    </ul>

    <hr />
    <div>
      <router-view></router-view>
    </div>

    <!-- <test v-if="showTest" msg="Props being passed down"></test> -->
    <!-- <users v-else></users> -->
  </div>
</template>

<script>
import Test from './components/Test';
import Users from './components/Users';

export default {
  name: 'App',
  data () {
    return {
      showTest: false
    }
  },
  components: {
    Test,
    Users
  }
}
</script>

<style>
ul {
  list-style: none;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
