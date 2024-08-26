<template>
  <div>
  <h1>{{ text }}</h1>
  <p>{{ para }}</p>
</div>
</template>
<script>
export default {
  name:'HeadingDemo',
  props: {
    text: {
      type: String,
      required: true
    },
    para: {
      type: String,
      required: true
    }
  }
}
</script>
