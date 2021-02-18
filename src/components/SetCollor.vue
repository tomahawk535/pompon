<template>
  <div class="select-size">
    <p class="color"
       @click="areOptionVisible=!areOptionVisible"
    >{{selectedC}}</p>
    <div class="color-option"
         v-if="areOptionVisible">
      <p class="color-option-item"
         v-for="color in selectedColor"
         :key="color.name"
         @click="selectColorOption(color)">
        {{color.name}}

      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SetColor",
  props: {
    selectedColor: {
      type: Array,
      default() {
        [ ]
      }
    },
    selectedC: {
      type : String,
      default: ''
    }
  },
  data (){
    return {
      areOptionVisible: false,

    }

  },
  methods: {
    selectColorOption(color){
      this.$emit('selectColorOp', color)
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
.color {
  width: 15rem;
  text-align: center;
  padding: 1rem 3rem;
  font-size: 1rem;
  text-transform: uppercase;
  background-color: #6fcaea;
}

</style>