<script setup>

import { reactive, ref, watch, watchEffect } from 'vue';
const formData = reactive({
  firstname:"",
  lastname:""
})
const description =ref('')
const anything = ref('')
const fullname = ref('');

watch(()=>formData,(n,o)=>{
  fullname.value = `${n.firstname} ${n.lastname}`
},{deep:true})

watchEffect(()=>{
  anything.value = description.value
})
</script>

<template>
  
  <div>
    Fullname:{{ fullname }} <br>
    <input type="text" v-model="formData.firstname">
    <input type="text" v-model="formData.lastname"><br>
    Description:{{ anything }} <br>
    <input type="text" v-model="description">
  </div>

</template>