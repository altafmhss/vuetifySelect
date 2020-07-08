<template>
<div id="app">
  <v-app id="inspire">
    <v-container fluid>
      <v-row align="center">
        <v-col class="d-flex" cols="12" sm="6">
         <v-select
                   
  item-text="name"
  item-value="name"
  v-model="form.bill_to_state"
  :items="people"
                   return-object
                   @change='getcode()'
>
        </v-col>
         <v-text-field v-model="form.bill_to_code" label="Bill To State Code" readonly></v-text-field>
      </v-row>
    <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-card-text>
      <div>{{form}}</div>
    </v-card-text>
  </v-card>
    </v-container>
  </v-app>
</div>
</template>

<script>
new Vue({
  el: '#app',
  vuetify: new Vuetify(),
  data: () => ({
      people: [
      {
        name: "abc",
        id: "1"
      },
      {
        name: "pqr",
        id: "2"
      },
      {
        name: "ghi",
        id: "3"
      }
    ],
     bill_to_code: 'hello',
    form: {
            bill_to_state: '',
          bill_to_code: '',
        },
  }),
  methods: {
   getcode: function () {
     this.form.bill_to_code=this.form.bill_to_state.id
   if (this.form.bill_to_state) {
     this.form.bill_to_state=this.form.bill_to_state.name;
   }
   } 
 }
})
</script>
