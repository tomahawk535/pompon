<template>
  <div class="t">
    <Tabs
        :tabs="tabs"
        :selected="selected"
        @selected="setSelected"
        >
        <Tab
          :isSelected="selected === 'Шаг 1: Выбор помпонов'">
          <SetCollor></SetCollor>
          <p>
            Seleted
          </p>
        </Tab>
        <Tab
          :isSelected="selected === 'Шаг 2: Доставка помпонов'" >
          <p>Some test text</p>
      </Tab>
      <Tab
          :isSelected="selected === 'Шаг 3: Подтверждение заказа'" >
          <p>Some test text3</p>
      </Tab>
    </Tabs>
  </div>
</template>

<script>
import Tabs from "@/components/Tabs";
import Tab from "@/components/Tab";
import SetCollor from "@/components/SetCollor";
export default {
name: "OrderInfo",
  components:{
    Tabs,
    Tab,
    SetCollor
  },
  data() {
    return {
      selected: 'Шаг 1: Выбор помпонов',
      tabs: [
        'Шаг 1: Выбор помпонов',
        'Шаг 2: Доставка помпонов',
        'Шаг 3: Подтверждение заказа',

      ]

    }
  },
  methods: {
    setSelected(tab) {
      this.selected = tab;
    }
  }

}
</script>

<style scoped>

</style>