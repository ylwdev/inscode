

<template>
  <div>
    <iItem />
  </div>
</template>

<script>
import iItem from './components/item.vue'

export default {
  components: {
    iItem
  },
  data() {
    return {
      isLogin: false
    }
  },
  methods: {
    handleLoginSuccess() {
      this.isLogin = true
    }
  }
}
</script>