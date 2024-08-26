<template>
  <button @click="handleClick" class="center">{{ label }}</button>
</template>
<script>
export default {    
  name:'ButtonDemo',
  props: {
    label: {
      type: String,
      required: true
    },
    action: {
      type: Function,
      required: true
    }
  },
  methods: {
    handleClick() {
      this.action();
    }
  }
}
</script>
