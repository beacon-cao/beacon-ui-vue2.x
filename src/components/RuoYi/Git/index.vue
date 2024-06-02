<template>
  <div>
    <svg-icon icon-class="github" @click="goto"/>
  </div>
</template>

<script>
export default {
  name: 'YudaoGit',
  data() {
    return {
      url: '源码地址url'
    }
  },
  methods: {
    goto() {
      window.open(this.url)
    }
  }
}
</script>
