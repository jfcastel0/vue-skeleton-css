<template>
  <div id="app" style="padding: 5px;">
    <Button primary>
      My Button
    </Button>
    <Button primary disabled>
      My Button
    </Button>
    <Button :loading="loading" @click="loading = !loading">
      My Button
    </Button>
    <Button  disabled>
      My Button
    </Button>
  </div>
</template>

<script>
  import Button from './components/Button.vue'

  export default {
    name: 'App',
    components: {
      Button
    },
    data() {
      return {
        loading: false
      }
    }
  }
</script>
