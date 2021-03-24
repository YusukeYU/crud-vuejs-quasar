<template>
  <div class="q-pa-md">
    <q-table
      :data="rows"
      row-key="name"
    />
  </div>
</template>

<script>
export default {
  data () {
    return {
      rows: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          sodium: 87,
          calcium: '14%',
          iron: '1%'
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          sodium: 129,
          calcium: '8%',
          iron: '1%'
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          sodium: 337,
          calcium: '6%',
          iron: '7%'
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          sodium: 413,
          calcium: '3%',
          iron: '8%'
        },
        {
          name: 'Gingerbread',
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          sodium: 327,
          calcium: '7%',
          iron: '16%'
        },
        {
          name: 'Jelly bean',
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          sodium: 50,
          calcium: '0%',
          iron: '0%'
        },
        {
          name: 'Lollipop',
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          sodium: 38,
          calcium: '0%',
          iron: '2%'
        },
        {
          name: 'Honeycomb',
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          sodium: 562,
          calcium: '0%',
          iron: '45%'
        },
        {
          name: 'Donut',
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          sodium: 326,
          calcium: '2%',
          iron: '22%'
        },
        {
          name: 'KitKat',
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          sodium: 54,
          calcium: '12%',
          iron: '6%'
        }
      ],
      name: '',
      backup: [],
      Current_Size: '',
      Prev_Size: 0
    }
  },
  props: {
    receiveRows: String
  },
  created () {
    // nós criamos um backup de acordo com as linhas atuais
    this.backup = this.rows
  },
  methods: {
    refreshTable () {
      // cria uma constante com o valor recebido convertido para caracteres minúsculos
      const stringConsulta = this.receiveRows.toLowerCase()
      // atribui o valor atual para o valor da string recebida
      this.Current_Size = stringConsulta.length
      // caso o usuário tenha apagado um caracter
      if (this.Current_Size < this.Prev_Size) {
        console.log('entrei no backup')
        this.rows = this.backup.filter(m => m.name.toLowerCase().indexOf(stringConsulta) > -1)
      } else { // caso o usuário NÃO tenha apagado um caracter
        this.rows = this.rows.filter(m => m.name.toLowerCase().indexOf(stringConsulta) > -1)
      }
      // atribui nosso valor anterior ao valor atual
      this.Prev_Size = this.Current_Size
    }
  },
  watch: { // caso tenha alguma alteração na receiveRows nós atualizamos a tabela
    receiveRows: function () {
      this.refreshTable()
    }
  }
}
</script>

<style scoped>

</style>
