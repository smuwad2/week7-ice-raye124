<script>
export default {
  data() {
    return {
      items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
      itemSelected: '' 
    }
  },
  methods: {
    deleteItem(item) {
      // filter removes the clicked item from the array
      this.items = this.items.filter(function(existingItem) {
        return existingItem !== item
      })
    },

    addItem() {
      // only add if not empty
      if (this.itemSelected.trim() !== '') {
        this.items.push(this.itemSelected)
        // clear the input box
        this.itemSelected = ''
      }
    }
  }
}
</script>

<template>
  <div>
    <h2>Shopping Cart</h2>

    <!-- Display list of items -->
    <ul>
      <li v-for="item in items" :key="item">
        {{ item }}
        <button @click="deleteItem(item)">Delete!</button>
      </li>
    </ul>

    <input type="text" v-model="itemSelected">

    <button @click="addItem">Add!</button>
  </div>
</template>
