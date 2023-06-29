<template>
    <div>
      <h1>
        {{ judul }}
      </h1>
    </div>
    <div v-if="showModal">
      <modal :header="header" :text="text" @close="openModal"/>
    </div>
    <button @click="openModal">open modal</button>
  </template>
  
  <script>
  
  export default{
    components:{
      modal
    },
      data(){
      return{
        judul : "hello",
        header : "Modal Content",
        text : "ini adalah custom modal",
        showModal : false
      }
    },
    methods :{
      handleClick(){
        console.log(this.$refs.tes)
        this.$refs.tes.classlist.add('ditekan')
        this.$refs.tes.focus()
      },
      openModal(){
        this.showModal = !this.showModal
      }
    }
  }
  import modal from '../components/modal.vue'
  
  </script>
  <style>
  h1{
    border-bottom: 1px solid #ddd;
    display : inline-block;
    padding-bottom: 10px;
  }
  </style>
  