<template>
  <img :src="`${publicPath}favicon.ico`" :alt="alt"/>
</template>
<script>

export default {
  name:'ImageDemo',
  props: {
    src: {
      type: String,
      required: true
      },
    alt: {
      type: String,
      default: ''
    }
  },
  data (){
    return {
      publicPath: process.env.BASE_URL,
    }
  }
}
</script>
