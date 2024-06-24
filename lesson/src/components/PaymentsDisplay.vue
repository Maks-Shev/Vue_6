<template>
  <div>
    <div v-for="item in items" :key="item.id">
      {{ item }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'PaymentsDisplay',
  props: {
    items: {
      type: Array,
      default () {
        return []
      }
    }
  },

  data () {
    return {

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
    }
  }
}
</script>
