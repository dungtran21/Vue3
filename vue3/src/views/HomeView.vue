<script setup>
import DtButton from '@/components/dt-button/DtButton.vue'
import DtBaseModal from '@/components/dt-modal/DtBaseModal.vue'
import DtInputSearch from '@/components/dt-input/DtInputSearch.vue'
import { ref } from 'vue'

function onAdd(event) {
  console.log('Thêm clicked', event)
}
const showModal = ref(false)
const searchQuery = ref('')
</script>

<template>
  <div class="card">
    <dt-button type="warning" positionIcon="left" icon="icon icon-add" @click="onAdd">
      Thêm
    </dt-button>
    <dt-base-modal v-model="showModal" title="Thêm ứng viên"> </dt-base-modal>
  </div>
  <br>
  <br>
  <dt-input-search v-model="searchQuery" placeholder="Tìm kiếm ứng viên..."/>
   <hr>
  <p>Giá trị hiện tại: {{ searchQuery }}</p>
<hr>
</template>
