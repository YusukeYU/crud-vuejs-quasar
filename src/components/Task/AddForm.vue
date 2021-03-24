<template>
  <div class="q-pa-md">

    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input color="blue-6" v-model="text" label="Título">
        <template v-slot:prepend>
          <q-icon name="task" />
        </template>
      </q-input>
      <q-input color="blue-6" v-model="date" label="Data">
        <template v-slot:prepend>
          <q-icon name="event_note" />
        </template>
      </q-input>
      <Calendar> </Calendar>
      <div>
        <q-btn v-on:click="showAddForm" label="Cancelar" color="primary"/>
        <q-btn label="Limpar" color="primary"/>
        <q-btn label="Cadastrar" color="primary"/>
      </div>
    </q-form>

  </div>
</template>

<script>
import Calendar from '../../components/Task/Calendar.vue'
export default {
  data () {
    return {
      text: '',
      date: ''
    }
  },
  components: {
    Calendar
  },
  methods: {
    showAddForm () {
      this.$emit('show')
    }
  }
}
</script>
<style scoped>
.q-pa-md{
  display: inline-block;
  text-align:center;
}
.q-field__inner {
    text-align: left;
    width: 400px!important;
}
.q-btn{
  margin-left:8px;
}
</style>
