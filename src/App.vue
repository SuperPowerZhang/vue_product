<template>
  <div id="app">
    <Header />
    <Main  :productList="productList"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

import  './css/init.css'
import  './css/base.css'


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    const productList=[{
      id:"0098",
      name:"电压力锅 一锅双胆 一键排压 精准控温",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },{
      id:"0097",
      name:"电压力锅 一锅双胆 一键排压 精准控温 304不锈钢智...",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },{
      id:"0096",
      name:"电压力锅 一锅双胆 一键排压 精准控温",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },{
      id:"0095",
      name:"电压力锅 一锅双胆 一键排压 精准控温 304不锈钢智...",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },{
      id:"0094",
      name:"电压力锅 一锅双胆 一键排压 精准控温",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },{
      id:"0093",
      name:"电压力锅 一锅双胆 一键排压 精准控温 304不锈钢智...",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },{
      id:"0092",
      name:"电压力锅 一锅双胆 一键排压 精准控温",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },{
      id:"0091",
      name:"电压力锅 一锅双胆 一键排压 精准控温 304不锈钢智...",
      type:"电压力锅",
      size:"CYSB50YCW10DJ-100",
      entry:'5',
    },
      {
        id:"0090",
        name:"电压力锅 一锅双胆 一键排压 精准控温",
        type:"电压力锅",
        size:"CYSB50YCW10DJ-100",
        entry:'5',
      },{
        id:"0089",
        name:"电压力锅 一锅双胆 一键排压 精准控温 304不锈钢智...",
        type:"电压力锅",
        size:"CYSB50YCW10DJ-100",
        entry:'5',
      },{
        id:"0088",
        name:"电压力锅 一锅双胆 一键排压 精准控温",
        type:"电压力锅",
        size:"CYSB50YCW10DJ-100",
        entry:'5',
      },{
        id:"0087",
        name:"电压力锅 一锅双胆 一键排压 精准控温 304不锈钢智...",
        type:"电压力锅",
        size:"CYSB50YCW10DJ-100",
        entry:'5',
      },
    ]
    return {productList}
  }
}
</script>

<style lang="scss">

</style>
