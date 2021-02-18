<template>
  <datepicker :value="state.date"
              :full-month-name="true"
              :placeholder="'Выберите дату'"


  >
    <div slot="beforeCalendarHeader" class="calender-header">
      Выберите дату
    </div>
  </datepicker>
</template>

<script>
import Datepicker from 'vuejs-datepicker';



export default {
name: "DatePicker",


  components:{
      Datepicker
  },
  data() {
    return {
      format: "d MMMM yyyy",
      // disabledDates: {},
      // disabledFn: {
      //   customPredictor(date) {
      //     if (date.getDate() % 3 === 0) {
      //       return true;
      //     }
      //   }
      // },
      state:{
        date: new Date( )
      },

    }
  }
}
</script>

<style scoped>

</style>