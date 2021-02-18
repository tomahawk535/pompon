<template>
  <div class="t">
    <Tabs
        :tabs="tabs"
        :selected="selected"
        @selected="setSelected"
        >
        <Tab class="tebb"
          :isSelected="selected === 'Шаг 1: Выбор помпонов'">
          <!-- all for select color -->
          <SetColor
              :selectedColor="pompons"
              @selectColorOp="selectColor"
              :selectedC="selectC"
          ></SetColor>
          <!-- all for select size-->
          <SelectSize
              :selectedSize="selectSize"
              @selectSizeOp="selectOption"
              :selectedS="selectedS"
          ></SelectSize>

          <!-- all for select quantity-->
          <SelectQuantuty
              :selectQuantity="quantity"
              @selectQuantityOp="selectQuantity"
              :selectedQ="selectedQ"
          ></SelectQuantuty>

          <!-- price for select -->
          <p  v-if="selectedS === '15 см'" class="price"> price {{selectedQ * 10}}</p>
          <p  v-else-if="selectedS === '25 см'" class="price"> price {{selectedQ * 20}}</p>
          <p  v-else-if="selectedS === '35 см'" class="price"> price {{selectedQ * 30}}</p>
          <p  v-else-if="selectedS === '45 см'" class="price"> price {{selectedQ * 40}}</p>
          <p  v-else class="price">you price</p>

        </Tab>
          <button
          @click="addOrder()"> wont more</button>
         <button
          @click="removeOrder()">Want less </button>
        <Tab
          :isSelected="selected === 'Шаг 2: Доставка помпонов'" >
          <Deliveryinfo></Deliveryinfo>

      </Tab>
      <Tab
          :isSelected="selected === 'Шаг 3: Подтверждение заказа'" >
          <p>Some test text3</p>
      </Tab>
    </Tabs>
    <p>selected option {{selectedQ}}</p>
  </div>
</template>

<script>
import Tabs from "@/components/Tabs";
import Tab from "@/components/Tab";
import SetColor from "@/components/SetCollor";
import Deliveryinfo from "@/components/Deliveryinfo";
import SelectSize from "@/components/SelectSize";
import SelectQuantuty from "@/components/SelectQuantuty";
export default {
name: "OrderInfo",
  components:{
    SelectQuantuty,
    SelectSize,
    Tabs,
    Tab,
    SetColor,
    Deliveryinfo,
  },
  data() {
    return {
      selected: 'Шаг 1: Выбор помпонов',
      tabs: [
        'Шаг 1: Выбор помпонов',
        'Шаг 2: Доставка помпонов',
        'Шаг 3: Подтверждение заказа',
      ],
      // order
      orders: [
        1
      ],
      // option for set color
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
      selectC: "Color",
      // option fo selectSize
      selectSize: [
        {name :'15 см', value: 1, price: 10},
        {name :'25 см', value: 2, price: 20},
        {name :'35 см', value: 3, price: 30},
        {name :'45 см', value: 4, price: 40},
      ],
      selectedS: 'Размер',
      // option for select quantity
      quantity: [
        { name: 10, value: 1},
        { name: "15", value: 2},
        { name: "20", value: 3},
        { name: "25", value: 4},
        { name: "30", value: 5},
        { name: "35", value: 6},
        { name: "40", value: 7},
        { name: "45", value: 8},
        { name: "50", value: 9},
        { name: "55", value: 10},
        { name: "60", value: 11},
        { name: "65", value: 12},
        { name: "70", value: 13},
        { name: "75", value: 14},
        { name: "80", value: 15},
        { name: "85", value: 16},
        { name: "90", value: 17},
        { name: "95", value: 18},
        { name: "100", value: 19},
      ],
      selectedQ:'Количество',


      sum: ""
    }
  },
  methods: {
    setSelected(tab) {
      this.selected = tab;
    },
    selectOption(selectedSize) {
      this.selectedS = selectedSize.name
      },
    selectColor (selectedColor) {
      this.selectC = selectedColor.name
    },
    selectQuantity(selectQuantity) {
      this.selectedQ = selectQuantity.name
    },
    // add new to order arr
    addOrder(){
      this.orders.push()
    },
    removeOrder(){
      this.orders.pop()
    }
  }

}
</script>

<style scoped>
  .tebb{
   display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
 }
  .price {
    background-color: #6fcaea;
  }
</style>