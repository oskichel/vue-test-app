<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button'
}
</script>

<style scoped>
.button {
  width: 284px;
  height: 36px;
  background: #7BAE73;;
  border-radius: 10px;
  outline: none;
  border: none;
  font-family: 'Inter';
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  line-height: 15px;
  text-align: center;
  letter-spacing: -0.02em;
  color: #FFFFFF;
}

.button:hover{
  cursor: pointer;
}

</style>