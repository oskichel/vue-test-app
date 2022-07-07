
<template>
  <div class="main-wrap">
    <h1 class="headline">Добавление товара</h1>
    <div class="container">
      <item-form
        @create="createItem"
      />
      <item-list 
        :items='items'
      />
    </div>
  </div>
</template>

<script>
import ItemForm from './components/ItemForm.vue';
import ItemList from './components/ItemList.vue';

export default {
  components: {
    ItemForm, ItemList
  },

  data() {
    return {
      items: [
        {id: 1, 
        img: 'https://imageup.ru/img44/3969230/img.jpg', 
        title: 'Наименование товара', 
        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', 
        price: '10 000 руб.'},
        {id: 2, 
        img: 'https://imageup.ru/img44/3969230/img.jpg', 
        title: 'Наименование товара', 
        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', 
        price: '10 000 руб.'},
        {id: 3, 
        img: 'https://imageup.ru/img44/3969230/img.jpg', 
        title: 'Наименование товара', 
        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', 
        price: '10 000 руб.'},
        {id: 4, 
        img: 'https://imageup.ru/img44/3969230/img.jpg', 
        title: 'Наименование товара', 
        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', 
        price: '10 000 руб.'},
      ],
    }
  },
  methods: {
    createItem(item) {
      this.items.push(item);
    },
  }
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', 'Inter', sans-serif; 
  background: rgba(255, 254, 251, 0.8);
}

.main-wrap {
  max-width: 1440px;
  margin: 0 auto;
}

.headline {
  margin: 32px 32px 0;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 600;
  font-size: 28px;
  line-height: 35px;
  color: #3F3F3F;
}

.container {
  padding: 16px 32px;
  display: flex;
  column-gap: 16px;
  box-sizing: border-box;
}

</style>
