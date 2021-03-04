<template>
  <div>
    <v-row justify="center"  no-gutters>
      <v-col cols="4" class="textbox_1 pt-5 pl-5">
        <v-row no-gutters>
          <v-col cols="9">
            <span class="headline">Total</span> <span class="display-1">Members :</span>
          </v-col>
          <v-col cols="1">
            <p class="text-right display-1 pl-15">5</p>
          </v-col>
          <v-col cols="9">
            <span class="headline">Total</span> <span class="display-1">Rev.</span><span class="title">(THB)</span>
          </v-col>
          <v-col cols="1">
            <p class="text-right display-1">639K</p>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="8" class="textbox_2 pt-2 pl-5 pr-3">
        <v-row no-gutters>
          <v-col cols="12">
            <p class="text-center headline">tttt</p>
          </v-col>
          <v-col cols="9">
            <span class="title">Total</span> <span class="headline">Members :</span>
          </v-col>
          <v-col cols="3">
            <p class="text-right headline">5</p>
          </v-col>
          <v-col cols="9">
            <span class="title">Total</span> <span class="headline">Rev : </span><span class="subtitle-1">(THB)</span>
          </v-col>
          <v-col cols="3">
            <p class="text-right headline">639K</p>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="12" class="mt-2">
        <v-data-table :headers="headers" :items="DataTable" :items-per-page="5" class="elevation-1">
          <template v-slot:item.customername="{ item }">
            <p class="text-left mt-5">{{item.customername}}</p>
          </template>
          <template v-slot:item.totalamount="{ item }">
            <p class="text-right mt-5">{{item.totalamount}}</p>
          </template>
          <template v-slot:item.totaltransaction="{ item }">
            <p class="text-right mt-5">{{item.totaltransaction}}</p>
          </template>
          <template v-slot:item.totalreward="{ item }">
            <p class="text-right mt-5">{{item.totalreward}}</p>
          </template>
          <template v-slot:item.remainingpoint="{ item }">
            <p class="text-right mt-5">{{item.remainingpoint}}</p>
          </template>
        </v-data-table>
      </v-col>
    </v-row>
  </div>
</template>
<script>

export default {
  data () {
    return {
      headers: [
        { text: 'Name', value: 'customername', align: 'center' },
        { text: 'ID', value: 'customerphone', align: 'center' },
        { text: 'Tier', value: 'customertier', align: 'center' },
        { text: 'LTV', value: 'totalamount', align: 'center' },
        { text: 'Total Trans.', value: 'totaltransaction', align: 'center' },
        { text: 'Total Point.', value: 'totalreward', align: 'center' },
        { text: 'Remaining Point.', value: 'remainingpoint', align: 'center' }
      ],
      DataTable: []
    }
  },
  async created () {
    var data = await this.axios.get('https://wegivmerchantapp.firebaseapp.com/exam/bi-member-day-2020-04-01.json')
    this.DataTable = data.data.data.list
  }
}
</script>
<style>
th, tr , td {
  border: 1px solid rgba(0, 0, 0, 0.12);
}
.textbox_1 {
  color: aliceblue;
  background-color: rgb(249, 145, 37);
  border-right: 1px solid aliceblue;
}
.textbox_2 {
  color: aliceblue;
  background-color: rgb(118, 115, 111);
}
</style>
