<template>
  <div id="app">
    <PaymentsDisplay :items="paymentsList" :info="infoText"/>
    <AddList @addNewPay="addNewPay"/>
  </div>
</template>

<script>
import AddList from './components/AddList.vue'
import PaymentsDisplay from './components/PaymentsDisplay.vue'

export default {
  name: 'App',
  components: {
    PaymentsDisplay,
    AddList
  },
  data () {
    return {
      paymentsList: []
    }
  },
  methods: {
    fetchData () {
      return [
        {
          date: '28.03.2023',
          category: 'Food',
          value: 169
        },
        {
          date: '24.03.2023',
          category: 'Transport',
          value: 360
        },
        {
          date: '24.03.2023',
          category: 'Food',
          value: 532
        }
      ]
    },
    addNewPay (data) {
      this.paymentsList.push(data)
    }
  },
  created () {
    this.paymentsList = this.fetchData()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
