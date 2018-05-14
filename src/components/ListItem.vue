<template>
  <span>
    <span class="product">{{item.product}}</span>
    <span class="quantity"><input type="number" v-model.number="item.quantity"></span>
    <span class="cost">{{item.cost * item.quantity}}</span>
  </span>
</template>

<script>
export default {
  name: 'ListItem',
  props: ['item']
}
</script>
