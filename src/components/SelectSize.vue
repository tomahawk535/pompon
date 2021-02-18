<template>
    <div class="select-size">
      <p class="size"
         @click="areOptionVisible=!areOptionVisible"
      >{{selectedS}}</p>
      <div class="size-option"
           v-if="areOptionVisible">
        <p class="size-option-item"
           v-for="size in selectedSize"
           :key="size.value"
           @click="selectSizeOption(size)">
          {{size.name}}
        </p>
      </div>
    </div>
</template>

<script>
export default {
name: "SelectSize",
  props: {
    selectedSize: {
      type: Array,
      default() {
        [ ]
      }
    },
    selectedS: {
      type : String,
      default: ''
    },
    orders: {
      type: Array,
      default() {
        []
      }
    }
  },
  data (){
    return {
      areOptionVisible: false,

    }

  },
  methods: {
    selectSizeOption(size){
      this.$emit('selectSizeOp', size)
      this.areOptionVisible = false;
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
  .size {
    width: 15rem;
    text-align: center;
    padding: 1rem 3rem;
    font-size: 1rem;
    text-transform: uppercase;
    background-color: #6fcaea;
  }
</style>