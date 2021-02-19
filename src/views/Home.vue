<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data: () => ({
    nginx_version: "foobar",
  }),
  created: function() {
  let vm = this
    fetch('https://kulturportal.de/de_DE/blog_articles.json').then((response) => {
      return response.json().then((json) => {
        console.log("JSON", json)
        vm.data = json
      })
    })
  }
}


</script>
