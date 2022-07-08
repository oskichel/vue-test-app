<template>
  <div class="items-container" v-if="items.length > 0">
    <product-item class="item" 
      v-for="(item) in items" 
      :item="item"
      :key="item.id"
      @remove="$emit('remove', item)"
    />
  </div>
  <h2 class="else" v-else>Список товаров пуст</h2>
</template>

<script>
import ProductItem from "./ProductItem.vue";


export default {
    props: {
        items: {
            type: Array,
            required: true
        }
    },
    components: {ProductItem }
}
</script>

<style scoped>
.item {
  width: 332px;
  height: 423px;
  background: #FFFEFB;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  box-sizing: border-box;
}

.item:hover {
  outline: 1px solid #7BAE73;
}

.items-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px 16px;
}

.else {
  margin: auto;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 600;
  font-size: 28px;
  line-height: 35px;
  text-align: center;
  color: #3F3F3F;
}

</style>