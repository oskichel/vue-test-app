<template>
  <textarea class="input" 
    :value="value"
    @input="updateInput"
    type='text'
  ></textarea>
</template>

<script>
export default {
  name: 'my-textarea',
  props: {
    value: [String, Number]
  },
  methods: {
    updateInput(event) {
      this.$emit('update:value', event.target.value)
    }
  }
}
</script>

<style scoped>
.input {
  width: 284px;
  min-height: 36px;
  margin-bottom: 16px;
  padding: 10px 16px 11px;
  background: #FFFEFB;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  border: none;
  box-sizing: border-box;
  resize: none;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 15px;
  color: #3F3F3F;
}

.input::placeholder {
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 15px;
  text-align: left;
  color: #B4B4B4;
}

.input:focus {
  border: none;
  outline: 1px solid #7BAE73;
}
</style>