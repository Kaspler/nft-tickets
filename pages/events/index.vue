<template lang="pug">
v-layout(column='', justify-center='', align-center='')
    v-flex(xs12='', sm8='', md6='')
        v-card(:width='640')
            v-card-title.headline Events
            v-card-text
                v-simple-table
                    thead
                        tr
                            th.text-left Name
                            th.text-left Date
                    tbody
                        tr(v-for="item in events" :key="item.name")
                            td {{ item.name }}
                            td {{ item.date }}

</template>

<script>
export default {
  data() {
    return {
      events: [
        {
          name: 'Monatik concert',
          date: 'December 1, 2019'
        },
        {
          name: 'Madonna concert',
          date: 'December 25, 2019'
        }
      ]
    }
  }
}
</script>

<style></style>
