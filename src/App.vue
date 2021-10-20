<template>
  <div id="app">
    <Home :msg="msg"/>
  </div>
</template>

<script>
import axios      from 'axios'
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  },
  data () {
    return {
      msg: null
    }
  },
  mounted () {
    axios
      .get('https://backend.demo.test/api/top-100-links')
      .then(response => (this.msg = response.data))
  }
}
</script>
