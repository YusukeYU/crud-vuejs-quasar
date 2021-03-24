<template>
<div class="q-gutter-y-md column">
  <q-input color="purple-12" v-model="text" label="Pesquisar">
    <template v-slot:prepend>
      <q-icon name="search" />
    </template>
  </q-input>
</div>
</template>

<style scoped>
.q-gutter-y-md{
max-width: 300px!important;
float:right;
padding-top:0;
margin-top:0;
}
.q-gutter-y-md > *, .q-gutter-md > * {
 margin-top:0;
}
</style>
