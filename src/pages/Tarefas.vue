<template>
  <div class="container">
    <div class="content">
      <div class="div-padrao-gus inputs">
        <BtnGroup></BtnGroup>
         <h2>Tarefas</h2>
        <SearchInput @changed="onChangeSearch"></SearchInput>
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
  },
  methods: {
    onChangeSearch (value) {
      console.log(value)
    }
  }
}
</script>

<style>
.div-padrao-gus{
float: left;
width: 100%;
text-align:center;
}
h2 {
margin: 0;
padding: 0;
font-size: 34px;
width: 63%;
padding-left: 43px;
float: left;
margin-top: 5px;
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
padding: 0 16px;
margin: 2rem 0 1.3rem 0;
}
</style>
