<template>
  <div class="header">
    <img :src="require('/src/assets/images/brand.png')" alt="logo">
    <div class="tel_numbers">
      <p v-for="number in tellNumbers"
         :key="number.id"
      > {{number.telNum}}</p>
    </div>


  </div>
</template>

<script>
export default {
name: "Header",
  data(){
    return {
      tellNumbers: [
        {telNum: '+380973597711'},
        {telNum:'+380638129000'}
      ]


    }
  }
}
</script>


<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  padding: 3rem 0;
  align-items: stretch;
  .tel_numbers {
    display: flex;
    align-items: baseline;
    flex-wrap: wrap;
  }
  p {
    color: #6fcaea;
    padding:  0 1rem;
    font-family: "Impact", sans-serif;
    font-size: 1.125rem;
    margin: 0.250rem;
    text-align: justify;
  }
}
</style>