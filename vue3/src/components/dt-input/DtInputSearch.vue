<template>
  <div class="wrap-search d-flex relative">
    <div class="search-container d-flex flex-align-baseline flex-1 relative">
      <div class="text-edit d-flex">
        <div class="icon icon-search"></div>
        <input
          class="input-cus"
          type="text"
          autocomplete="off"
          style="min-height: 0px"
          :placeholder="props.placeholder"
          :value="modelValue"
          @input="onInput"
          id="a"
          name="b"
        />
      </div>
    </div>
  </div>
</template>
<script setup>
const emit = defineEmits(['update:modelValue'])
const props = defineProps({
  placeholder: {
    type: String,
    default: 'Tìm kiếm...',
  },
  modelValue: {
    type: String,
    default: '',
  },
})
props
//#region Methods
/**
 * hàm xử lý nhập input
 * @param e
 * createdby: dungtv - 04.11.2025
 */
function onInput(e) {
  const value = e.target.value
  emit('update:modelValue', value)
}
</script>
<style scoped>
.wrap-search {
  flex-grow: 1;
  min-width: 0;
}
.search-container {
  align-items: center;
  width: auto;
  height: 32px;
  background: #f2f2f2;
  padding: 0 8px;
}
.text-edit {
  position: relative;
  flex-grow: 1;
  min-width: 0;
  overflow: hidden;
}
.input-cus {
  border: none;
  outline: none;
  flex: 1 1 auto;
  min-width: 0;
  width: 100%;
  background: transparent;
}
</style>
