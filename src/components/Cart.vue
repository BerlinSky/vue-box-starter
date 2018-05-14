<template>
  <div>
    <h2>Shopping List</h2>
    <ol id="list">
      <li v-for="(item, index) in cart" :key="index">
        <list-item :item="item" />
      </li>
    </ol>
    <div>
      Total = USD {{totals}}
    </div>
  </div>
</template>

<script>
import ListItem from './listItem'

const products = [
  {
    product: 'Ben & Jerry\'s Coconut Seven',
    cost: 30,
    quantity: 2
  }, {
    product: 'Lipton Honey Lemon Green Tea',
    cost: 10,
    quantity: 6
  }, {
    product: 'Lindt Lindor - Milk Truffles',
    cost: 100,
    quantity: 1
  }, {
    product: 'Ferrero Rocher (24 Pieces)',
    cost: 12,
    quantity: 4
  }, {
    product: 'Goodwyn Tea',
    cost: 20,
    quantity: 8
  }, {
    product: 'Typhoo Treasures Green Tea',
    cost: 5,
    quantity: 10
  }
]
export default {
  name: 'Cart',
  data () {
    return {
      cart: products
    }
  },
  components: {
    ListItem
  },
  computed: {
    totals () {
      return this.cart.reduce(function (total, item) {
        return total + (item.cost * item.quantity)
      }, 0)
    }
  }
}
</script>
