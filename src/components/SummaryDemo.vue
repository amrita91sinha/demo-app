<template>
  <div>
    <h3>{{ title }}</h3>
    <p><strong>Name:</strong> {{ formData.name }}</p>
    <p><strong>Email:</strong> {{ formData.email }}</p>
    <p><strong>Password:</strong> {{ maskedPassword }}</p>
  </div>
</template>

<script>
export default {
  name: 'SummaryDemo',
  props: {
    title: String,
    formData: {
      type: Object,
      default() {
        return {
          name: '',
          email: '',
          password: ''
        };
      }
    }
  },
  computed: {
    maskedPassword() {
      return '*'.repeat(this.formData.password ? this.formData.password.length : 0);
    }
  }
};
</script>

<style scoped>
h3 {
  font-family: 'Arial', sans-serif;
  color: #333;
  margin-bottom: 10px;
}

p {
  font-family: 'Arial', sans-serif;
  color: #555;
  margin: 5px 0;
}
</style>
