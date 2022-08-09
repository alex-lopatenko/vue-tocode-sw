<template>
  <div class="md-body">
    <h1>Hello home</h1>
    <p>Edit me</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, ref } from 'vue'
import DataService from '@/services/DataService'
import ResponseData from '@/types/ResponseData'
import Peoples from '@/types/Peoples'

export default defineComponent({
  setup() {

    const loading = ref(true as boolean)
    const peoples = ref({} as Peoples)

    onMounted(() => getPeople())

    const getPeople = () =>
      DataService.getAll()
      .then((res: ResponseData) => {
        peoples.value = res.data
        loading.value = false
        })
      .catch((e:Error) => console.log(e))

    console.log(peoples)
    
  }
})
</script>