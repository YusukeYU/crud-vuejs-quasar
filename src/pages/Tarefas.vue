<template>
  <div>
    <div class="teste">
      <h1 class="fixed-center">Tarefas</h1>
    </div>
    <DataTable></DataTable>
  </div>
</template>

<script>
import DataTable from '../components/DataTable.vue'
export default {
  name: 'PageTarefas',
  components: {
    DataTable
  }
}
</script>

<style scoped>
.teste{
float:left;
      }
h1 {
    font-size: 3rem;
   }
.fixed-center
{
 top:6%;
}
</style>
