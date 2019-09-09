<template lang="pug">
v-layout(column='', justify-center='', align-center='')
    v-flex(xs12='', sm8='', md6='')
        v-card(:width='640')
            v-card-title.headline Event: Madonna concert
            v-card-text
                v-label Date: 25 December, 2019
                v-simple-table
                    thead
                        tr
                            th.text-left ID
                            th
                    tbody
                        tr(v-for="item in tickets" :key="item.name")
                            td {{ item.name }}
                            td
                                v-row(justify="center")
                                    v-dialog(v-model="dialog" persistent="" max-width="600px")
                                        template(v-slot:activator="{ on }")
                                            v-btn(color="primary" dark="" v-on="on") Transfer
                                        v-card
                                            v-card-title
                                                span.headline Transfer
                                            v-card-text
                                                v-container
                                                    v-row
                                                        v-col(cols="12")
                                                            v-text-field(label="Email or Tezos address*" required="")
                                                small *indicates required field
                                            v-card-actions
                                                .flex-grow-1
                                                v-btn(color="blue darken-1" text="" @click="dialog = false") Close
                                                v-btn(color="blue darken-1" text="" @click="dialog = false") Save
                                td
                                    v-btn(color="primary" dark="" v-on="on") View
                v-text-field(v-model='ticketsNumber' label='Number of tickets')
                br
                v-btn(color='secondary') Create tickets
            v-card-actions
                v-spacer
                v-btn(color='primary') Edit event details
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
      tickets: [
        {
          name: '8748872'
        },
        {
          name: '8748873'
        }
      ]
    }
  }
}
</script>

<style></style>
