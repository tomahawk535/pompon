<template>
  <div class="select-quantity">
    <p class="quantity"
       @click="areOptionVisible=!areOptionVisible"
    >{{selectedQ}}</p>
    <div class="quantity-option"
         v-if="areOptionVisible">
      <p class="quantity-option-item"
         v-for="quantity in selectQuantity"
         :key="quantity.value"
         @click="selectQuantityOption(quantity)">
        {{quantity.name}}

      </p>
    </div>
  </div>
</template>

<script>
export default {
name: "SelectQuantuty",
  props: {
    selectQuantity: {
      type: Array,
      default() {
        []
      }
    },
    selectedQ: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      areOptionVisible: false,
    }
  },

  methods:{
    selectQuantityOption(quantity) {
      this.$emit('selectQuantityOp', quantity)
    },
    hideSelect() {
      this.areOptionVisible = false;
    },
  },
  mounted() {
    document.addEventListener( "click", this.hideSelect.bind(this), true)
  },
  beforeDestroy() {
    document.removeEventListener( 'click',  this.hideSelect)
  }
}
</script>

<style scoped>
.quantity {
  width: 15rem;
  text-align: center;
  padding: 1rem 3rem;
  font-size: 1rem;
  text-transform: uppercase;
  background-color: #6fcaea;
}
</style>