<template>
  <div id="app">
    <img alt="Vue logo" src="https://vuejs.org/images/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import EssentialLink from './components/EssentialLink.vue'
import MainLayout from './components/MainLayout.vue'

export default [
{
    name: '1',
    icon: 'settings',
    permission: 'configuration',
    description: '1',
    url: '',
    children: [
      {
        name: '1.1',
        permission: 'configuration',
        url: '/insuranceTypes',
        icon: 'add',
        description: '1.1'
      },
      {
        name: '1.2',
        permission: 'configuration',
        url: '/insuranceTypes2',
        icon: 'phone',
        description: '1.2'
      }
    ]
  }, {
    name: '2',
    icon: 'person',
    permission: 'configuration',
    url: 'contacts',
    description: '2'
  }
  ]
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>


