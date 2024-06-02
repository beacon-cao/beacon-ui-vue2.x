<template>
  <div>
    <svg-icon icon-class="question" @click="goto"/>
  </div>
</template>

<script>
export default {
  name: 'YudaoDoc',
  data() {
    return {
      url: '文档地址url'
    }
  },
  methods: {
    goto() {
      window.open(this.url)
    }
  }
}
</script>
