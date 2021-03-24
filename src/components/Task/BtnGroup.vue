<template>
    <q-btn-group push>
      <q-btn  v-on:click="showAddForm" push label="Adicionar" icon="addchart" />
    </q-btn-group>
</template>

<script>
export default {
  methods: {
    showAddForm () {
      this.$emit('show')
    }
  }
}
</script>

<style scoped>
.q-btn-group {
float:left;
margin-top: 19px;
}
</style>
