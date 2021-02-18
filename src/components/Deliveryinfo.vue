<template>
  <div class="delivery_info">
    <DatePicker></DatePicker>
    <AdressSelection></AdressSelection>
    <h1>DATA PIKER</h1>
  </div>
</template>

<script>
import DatePicker from "@/components/DatePicker";
import AdressSelection from "@/components/AdressSelection";
export default {
name: "Deliveryinfo",
  components:{
    DatePicker,
    AdressSelection
  }
}
</script>

<style scoped>

</style>