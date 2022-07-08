<template>
  <div>
    <form class="form" @submit.prevent>
      <label class="label" for="title">Наименование товара</label>
      <span class="star">*</span>
      <my-input 
        v-model:value="item.title"
        type="text" 
        id="title"
        placeholder="Введите наименование товара"
      />

      <label class="label" for="body">Наименование товара</label>
      <span class="star">*</span>
      <my-textarea class="body"
        v-model:value="item.body"
        type="text" 
        id="body"
        placeholder="Введите описание товара"
      />

      <label class="label" for="img">Наименование товара</label>
      <span class="star">*</span>
      <my-input 
        v-model:value="item.img"
        type="text" 
        id="img"
        placeholder="Введите ссылку"
      />

      <label class="label" for="price">Наименование товара</label>
      <span class="star">*</span>
      <my-input 
        v-model:value="item.price"
        type="text" 
        id="price"
        placeholder="Введите цену"
      />

      <my-button
        @click="createItem"
      >Добавить товар</my-button>
    </form>
  </div>
</template>

<script>
export default {
    data() {
        return {
            item: {
                title: "",
                body: "",
                price: "",
                img: "",
            }
        };
    },
    methods: {
        createItem() {
            this.item.id = Date.now();
            this.$emit("create", this.item);
            this.item = {
                title: "",
                body: "",
                price: "",
                img: "",
            };
        }
    },
}
</script>

<style scoped>
.form {
  width: 332px;
  height: 440px;
  padding: 24px;
  background: #FFFEFB;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  box-sizing: border-box;
}

.label {
  padding-bottom: 4px;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 13px;
  letter-spacing: -0.02em;
  color: #49485E;
  box-sizing: border-box;
}

.star {
  color: #FF8484;
  padding-bottom: 4px;
  line-height: 13px;
  box-sizing: border-box;
}

.body {
  height: 108px;
}

</style>