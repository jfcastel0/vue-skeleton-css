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

    <ul>
      <li>one</li>
        <ol>
          <li>again</li>
        </ol>
    </ul>

    <div class="container">
      <Row>
        <Col cols="one">
          <div style="background-color: purple;">Three</div>
        </Col>
        <Col cols="three">
          <div style="background-color: yellow;">Nine</div>
        </Col>
        <Col cols="six">
          <div style="background-color: yellow;">Nine</div>
        </Col>
        <Col>
          <div style="background-color: yellow;">Nine</div>
        </Col>
        <!-- <Col>
          <div style="background-color: yellow;">Nine</div>
        </Col>
        <Col>
          <div style="background-color: yellow;">Nine</div>
        </Col>
        <Col>
          <div style="background-color: yellow;">Nine</div>
        </Col>
        <Col>
          <div style="background-color: yellow;">Nine</div>
        </Col> -->
      </Row>
    </div>
  </div>
</template>

<script>
  import Button from './components/Button.vue'
  import Row from './components/Row.vue'
  import Col from './components/Col.vue'

  export default {
    name: 'App',
    components: {
      Button,
      Row,
      Col
    },
    data() {
      return {
        loading: false
      }
    }
  }
</script>
