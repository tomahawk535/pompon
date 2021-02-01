<template>
  <div class="set_color">
    <select class="collor" v-model="selectColor">
      <option class="collor-item"
      v-for="pompon in pompons" :key="pompon.name" v-bind:value="pompon.img">{{pompon.name}}</option>
    </select>
      <p>select pompon is {{selectColor}}</p>
  </div>
</template>

<script>
export default {
name: "SetCollor",
  pops: {
  },
  data() {
    return{
        pompons: [
          {
            'name': 'Black',
            'img': 'bk.png'
          },
          {
            'name': 'Blue',
            'img': 'bl.png'
          },
          {
            'name': 'Ceris',
            'img': 'cs.png'
          },
          {
            'name': 'Green',
            'img': 'gn.png'
          },
          {
            'name': 'Ivory',
            'img': 'iv.png'
          },
          {
            'name': 'light Blue',
            'img': 'lb.png'
          },
          {
            'name': 'Lavander',
            'img': 'ld.png'
          },
          {
            'name': 'Blue',
            'img': 'bl.png'
          },
          {
            'name': 'Lilac',
            'img': 'll.png'
          },
          {
            'name': 'Mint',
            'img': 'mt.png'
          },
          {
            'name': 'Orange',
            'img': 'og.png'
          },
          {
            'name': 'Peach',
            'img': 'ph.png'
          },
          {
            'name': 'Pink',
            'img': 'pk.png'
          },
          {
            'name': 'Purple',
            'img': 'pr.png'
          },
          {
            'name': 'Red',
            'img': 'rd.png'
          },
          {
            'name': 'White',
            'img': 'wh.png'
          },
          {
            'name': 'Yellow',
            'img': 'yw.png'
          },
        ],
      selectColor: ''
    }

  },
  methods:{
      setColor (selectColor){
        this.$emit ('selectColl', selectColor)
      }
  }


}



</script>

<style scoped>
.set_color {margin: 2rem 0}
.collor {
  width: 15rem;
  text-align: center;
  padding: 1rem 3rem;
  font-size: 1rem;
  text-transform: uppercase;
}
.collor-item {
  background-color: blueviolet;
  text-transform: uppercase;
  padding: 0 4rem;
}
</style>