<template>
  <div class="container">
    <div class="content">
      <div class="div-padrao-gus">
        <h1 class="">Tarefas</h1>
      </div>
      <div class="div-padrao-gus inputs">
        <BtnGroup></BtnGroup>
        <SearchInput></SearchInput>
      </div>
      <div class="div-padrao-gus">
        <DataTable></DataTable>
      </div>
    </div>
  </div>
</template>

<script>
import DataTable from '../components/DataTable.vue'
import BtnGroup from '../components/Task/BtnGroup.vue'
import SearchInput from '../components/Task/SearchInput.vue'
export default {
  name: 'PageTarefas',
  components: {
    DataTable,
    BtnGroup,
    SearchInput
  }
}
</script>

<style>
.div-padrao-gus{
float: left;
width: 100%;
text-align:center;
}
h1 {
font-size: 2rem;
position:relative!important;
line-height: 3rem;
margin: 2rem 0;
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
.inputs{
margin-bottom:2rem;
padding: 0 16px;
}
</style>
