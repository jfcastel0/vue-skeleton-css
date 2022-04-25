<template>
  <div id="app" style="padding: 5px;">
    <Button primary  :loading="loading" @click="loading = !loading">
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
    <Heading size="h1">Heading</Heading>
    <Heading size="h2">Heading</Heading>
    <Heading size="h3">Heading</Heading>
    <Heading size="h4">Heading</Heading>
    <Heading size="h5">Heading</Heading>
    <Heading size="h6">Heading</Heading>
  </div>
</template>

<script>
  import Button from './components/Button.vue'
  import Heading from './components/Heading.vue'

  export default {
    name: 'App',
    components: {
      Button,
      Heading
    },
    data() {
      return {
        loading: false
      }
    }
  }
</script>
