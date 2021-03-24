<template>
<div class="q-gutter-y-md column">
  <q-input color="purple-12" v-model="name"  label="Pesquisar">
    <template v-slot:prepend>
      <q-icon name="search" />
    </template>
  </q-input>
</div>
</template>

<script>
export default {
  data () {
    return {
      name: '',
      change: false
    }
  },
  watch: {
    name: function () {
      this.changeSearch()
    }
  },
  methods: {
    changeSearch () {
      this.$emit('changed', this.name)
    }
  }
}
</script>

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
