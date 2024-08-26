<template>
  <div>
    <label>{{ label }}</label>
    <input v-model="inputValue" @input="updateData" :type="type" />
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    type: {
      type: String,
      default: 'text'
    }
  },
  data() {
    return {
      inputValue: ''
    };
  },
  methods: {
    updateData() {
      this.$emit('updateData', { key: this.label.toLowerCase(), value: this.inputValue });
    }
  }
}
</script>
