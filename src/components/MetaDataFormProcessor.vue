<template>
  <div>
    <component
      v-for="(comp, index) in components"
      :key="index"
      :is="resolveComponent(comp.type)"
      v-bind="resolveProps(comp.props)"
      @updateData="updateFormData"
    />
    <SummaryDemo :title="'Summary of Input Data'" :formData="formData" />
  </div>
</template>

<script>
import InputField from './InputField.vue';
import ButtonDemo from './ButtonDemo.vue';
import SummaryDemo from './SummaryDemo.vue';
import HeadingDemo from './HeadingDemo.vue';

export default {
  name: 'MetaDataFormProcessor',
  props: {
    components: {
      type: Array,
      required: true
    }
  },
  components: {
    ButtonDemo,
    InputField,
    SummaryDemo,
    HeadingDemo
  },
  data() {
    return {
      formData: {
        name: '',
        email: '',
        password: ''
      }
    };
  },
  methods: {
    resolveComponent(type) {
      const resolvedComponent = this.$options.components[type];
      return resolvedComponent || 'div';
    },
    resolveProps(props) {
      if (typeof props.action === 'string' && this[props.action]) {
        props.action = this[props.action];
      }
      return props;
    },
    updateFormData(newData) {
      // Update formData with the new data emitted from InputField
      this.formData = { ...this.formData, [newData.key]: newData.value };
    },
    handleSubmit() {
      console.log('Form submitted:', this.formData);
      // Additional submit logic can be implemented here
    }
  }
};
</script>
