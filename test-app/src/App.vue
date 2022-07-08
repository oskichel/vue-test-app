
<template>
  <div class="main-wrap">
    <div class="header-wrap">
      <h1 class="headline">Добавление товара</h1>
      <my-select 
        v-model="selectedSort"
        :options="sortOptions"
      />
    </div>
    <div class="container">
      <item-form
        @create="createItem"
      />
      <item-list 
        :items='items'
        @remove="removeItem"
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
        price: '20000'},
        {id: 2, 
        img: 'https://imageup.ru/img44/3969230/img.jpg', 
        title: 'Наименование товара', 
        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', 
        price: '10000'},
        {id: 3, 
        img: 'https://imageup.ru/img44/3969230/img.jpg', 
        title: 'Наименование товара', 
        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', 
        price: '50000'},
        {id: 4, 
        img: 'https://imageup.ru/img44/3969230/img.jpg', 
        title: 'Наименование товара', 
        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', 
        price: '30000'},
      ],
      selectedSort: '',
      sortOptions: [
        {value: 'title', name: 'По наименованию'},
        {value: 'price', name: 'По возрастанию'},
      ]
    }
  },
  methods: {
    createItem(item) {
      this.items.push(item);
    },
    removeItem(item) {
      this.items = this.items.filter(i => i.id !== item.id)
    }
  },
  watch: {
    selectedSort(newValue) {
      this.items.sort((item1, item2) => {
        return item1[newValue]?.localeCompare(item2[newValue])
      })
    }
  }
}
</script>

<style scoped>
html {
  font-family: 'Source Sans Pro', 'Inter', sans-serif; 
  background: rgba(255, 254, 251, 0.8);
  margin: 0;
  padding: 0;
}

.main-wrap {
  max-width: 1440px;
  margin: 0 auto;
  padding: 0 22px;
}

.header-wrap {
  display: flex;
  justify-content: space-between;
  align-items: end;
}

.headline {
  margin: 32px 0 0;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 600;
  font-size: 28px;
  line-height: 35px;
  color: #3F3F3F;
}

.container {
  padding: 16px 0;
  display: flex;
  column-gap: 16px;
  box-sizing: border-box;
}

</style>
