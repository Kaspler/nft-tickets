<template lang="pug">
v-layout(column='', justify-center='', align-center='')
  v-flex(xs12='', sm8='', md6='')
    v-card(:width='640')
      v-card-title.headline Create new event
      v-card-text
        v-form
          v-text-field(v-model='name' label='Event name')
          v-textarea(v-model='description' label='Event description')
          v-label Event date
          br
          v-date-picker(v-model="date" label='Date')
          br
          v-switch(v-model="ticketsWithBalance" :label="`Tickets with balance`")
      v-card-actions
        v-spacer
        v-btn(nuxt='', to='/inspire')
          | Continue

</template>

<script>
export default {
  data() {
    return {
      name: '',
      description: '',
      ticketsWithBalance: '',
      date: new Date().toISOString().substr(0, 10)
    }
  }
}
</script>

<style></style>
