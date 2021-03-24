<template>
  <div class="container">
    <div class="content">
      <div class="div-padrao-gus">
        <h1 class="">Tarefas</h1>
      </div>
      <div class="div-padrao-gus">
        <DataTable></DataTable>
      </div>
    </div>
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

<style>
.div-padrao-gus{
float: left;
width: 100%;
}
h1 {
font-size: 3rem;
position:relative!important;
}
.fixed-center
{
 top:6%;
}
.container{
max-width: 980px;
margin-left: auto;
margin-right: auto;
height: auto;
position: relative;
border-radius: 3px;
}
.content{
position : relative;
width:100%;
float :left;
text-align:center;
justify-items:center;
}
.q-pa-md{
position: relative;
padding-top:0;
}
</style>
