<template>
  <div>
    <img class="img" :src="item.img">
    <div class="wrap">
        <h2 class="title">{{ item.title }}</h2>
      <div class="body">{{ item.body }}</div>
      <div class="price">{{ item.price }}</div>
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
  }
}
</script>

<style scoped>
.img {
  width: 332px;
  height: 200px;
  border-top-left-radius: 4px;
  border-top-right-radius: 4px;
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