<template>
  <div class="wrap">
    <Header></Header>
    <Slic_carousel class="car"></Slic_carousel>
    <Orderinfo></Orderinfo>
  </div>
</template>

<script>
import Header from "@/components/Header";
import Slic_carousel from "@/components/Slic_carousel";
import Orderinfo from "@/components/Orderinfo";
export default {
name: "Wrap",
  components: {
    Header,
    Slic_carousel,
    Orderinfo
  }

}
</script>

<style lang="scss" scoped>
.wrap {
  padding: 0 10%;
  background-color: #2c3e50;
}
.car {
  width: 100%;
  margin: 0 auto;
}
</style>