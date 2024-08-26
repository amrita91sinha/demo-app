<template>
  <input v-model="formData" @input="updateData" />
</template>
<script>
export default {
  name:'FormDemo',
  data() {
    return {
      formData: ''
    };
  },
  methods: {
    updateData() {
      this.$emit('updateData', this.formData);
    }
  }
}
</script>
