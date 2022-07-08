<template>
  <select class="select" :value="modelValue" @change="changeOption">
    <option disabled value="">По умолчанию</option>
    <option 
      v-for="option in options" 
      :key="option.value"
      :value="option.value"
    >
    {{ option.name }}
    </option>
  </select>
</template>

<script>
export default {
  name: 'my-select',
  props: {
    modelValue: {
      type: String
    },
    options: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    changeOption(event) {
      this.$emit('update:modelValue', event.target.value);
    }
  }
}
</script>

<style scoped>
.select {
  width: 136px;
  height: 36px;
  margin-right: 20px;
  padding: 10px 0 11px 16px;
  background-color: #FFFEFB;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  outline: none;
  border: none;
  box-sizing: border-box;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 15px;
  color: #B4B4B4;
}

</style>