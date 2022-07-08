<template>
  <div class="single-item">
    <button class="delete" @click="$emit('remove', item)"><img src="../assets/icons/delete.png"></button>
    <img class="img" :src="item.img">
    <div class="wrap">
        <h2 class="title">{{ item.title }}</h2>
      <div class="body">{{ item.body }}</div>
      <div class="price">{{ item.price }} руб.</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    }
  },
}
</script>

<style scoped>
.single-item{
  position: relative;
  box-sizing: border-box;
}

.img {
  width: 332px;
  height: 200px;
  border-top-left-radius: 4px;
  border-top-right-radius: 4px;
}

.delete {
  z-index: 10;
  position: absolute;
  top: -7px;
  right: -7px;
  width: 32px;
  height: 32px;
  background: #FF8484;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  box-sizing: border-box;
  border: none;
  outline: none;
  /*display: none;*/
}

.delete:hover {
  cursor: pointer;
}

.wrap {
  margin: 16px 16px 24px;
  display: block;
}

.title {
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 25px;
  color: #3F3F3F;
}

.body {
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 20px;
  color: #3F3F3F;
}

.price {
  padding-top: 32px;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 600;
  font-size: 24px;
  line-height: 30px;
  color: #3F3F3F;
}

</style>