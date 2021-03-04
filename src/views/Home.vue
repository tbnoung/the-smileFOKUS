<template>
  <a-layout>
    <a-layout-header :style="{ padding: '0', background: '#fff', position: 'fixed', zIndex: 1, width: '100%' }">
      <a-row type="flex">
        <a-col :span="18" class="background_header">
            <a-col :span="10" class="pl-15">
              <img src="@/assets/A.png" class="img_logo">
            </a-col>
            <a-col :span="14" class="pl-15">
              <a-row type="flex" justify="end">
                <v-icon large dark>mdi-account-circle-outline</v-icon>
                <span class="mr-5 font_color">MR.ADMIN</span>
              </a-row>
            </a-col>
        </a-col>
        <a-col :span="6" class="background_header2">
          <a-row type="flex" justify="end">
            <span class="mr-3" style="color:white">MENU</span>
            <v-icon class="mr-5" large>mdi-cloud-outline</v-icon>
          </a-row>
        </a-col>
      </a-row>
    </a-layout-header>
    <a-layout-content :style="{ padding: '0 50px', marginTop: '64px' }">
      <a-row type="flex">
        <a-col :span="16">
          <a-breadcrumb :style="{ margin: '16px 0' }">
            <a-breadcrumb-item><v-icon small>mdi-home-outline</v-icon></a-breadcrumb-item>
            <a-breadcrumb-item>Business Insight</a-breadcrumb-item>
            <a-breadcrumb-item>Report</a-breadcrumb-item>
            <a-breadcrumb-item>Member</a-breadcrumb-item>
            <a-breadcrumb-item><span class="title font_color">Member</span></a-breadcrumb-item>
          </a-breadcrumb>
        </a-col>
        <a-col :span="8">
          <a-row type="flex" justify="end">
            <v-avatar size="40" class="mt-3 mr-3" v-for="item in 3" :key="item">
              <v-img src="@/assets/diagram.png" />
            </v-avatar>
          </a-row>
        </a-col>
      </a-row>
      <a-row type="flex">
        <a-col :span="16">
          <span class="font_color headline mr-3">Yearly Mamber</span><span class="font_color title">01-Jan-2020 to 31-Dec-2020</span>
        </a-col>
        <a-col :span="8">
          <a-row type="flex" justify="end" class="mb-3">
            <a-select default-value="Year View" style="width: 120px">
              <a-select-option value="Year View"> Year View</a-select-option>
            </a-select>
            <a-date-picker  default-value="2021/04/04" />

          </a-row>
        </a-col>
      </a-row>
      <div :style="{ minHeight: '380px' }">
        <Table />
      </div>
    </a-layout-content>
    <a-layout-footer :style="{ padding: '0', background: '#fff', marginTop: '95vh', height:'5vh', position: 'fixed', zIndex: 1, width: '100%' }">
      <a-row type="flex">
        <v-container grid-list-xs>
          <a-col :span='10'>
            <span class="font_color">Total</span>
          </a-col>
          <a-col :span='14'>
            <a-row type="flex" justify="space-between">
              <span class="font_color">639,498</span>
              <span class="font_color">7</span>
              <span class="font_color">47,699</span>
              <span class="font_color">47,699</span>
            </a-row>
          </a-col>
        </v-container>
      </a-row>
    </a-layout-footer>
  </a-layout>
</template>
<script>
import Table from './Table'
export default {
  components: {
    Table
  },
  data () {
    return {
      selectItem: 'Year View',
      items: ['Year View']
    }
  }
}
</script>
<style>
#components-layout-demo-fixed .logo {
  width: 120px;
  height: 31px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px 24px 16px 0;
  float: left;
}
.img_logo {
  max-width: 90px;
  margin-bottom: 10px;
}
.background_header {
  background-color: black;
}
.background_header2 {
  background-color: rgb(249, 145, 37);
}
.background_footer {
  background-color: white;
}
.font_color {
  color: orange;
}
</style>
