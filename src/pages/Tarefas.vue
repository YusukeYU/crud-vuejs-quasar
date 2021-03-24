<template>
  <div class="container">
    <div class="content">
      <div v-if="showListComponents">
        <div class="div-padrao-gus inputs">
          <BtnGroup @show="showAddFormFunction"></BtnGroup>
           <h2>Tarefas</h2>
          <SearchInput @changed="onChangeSearch"></SearchInput>
        </div>
        <div class="div-padrao-gus">
        <DataTable v-bind:receiveRows="name"></DataTable>
        </div>
      </div>
      <div class="div-padrao-gus">
        <AddForm @show="showAddFormFunction" v-if="showAddForm"> </AddForm>
      </div>
    </div>
  </div>
</template>

<script>
import DataTable from '../components/DataTable.vue'
import BtnGroup from '../components/Task/BtnGroup.vue'
import SearchInput from '../components/Task/SearchInput.vue'
import AddForm from '../components/Task/AddForm.vue'

export default {
  name: 'PageTarefas',
  data () {
    return {
      name: '',
      showAddForm: false,
      showListComponents: true
    }
  },
  components: {
    DataTable,
    BtnGroup,
    SearchInput,
    AddForm
  },
  methods: {
    // sempre que o valor do input search for alterado ele entrará na função abaixo passando o valor atual
    onChangeSearch (value) {
      this.name = value
    },
    showAddFormFunction () {
      this.showAddForm = !this.showAddForm
      this.showListComponents = !this.showListComponents
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
