<template>
  <Teleport to="body">
    <div v-if="modelValue">
      <!-- modal -->
      <div class="dt-modal">
        <!-- header-modal  -->
        <div class="dt-modal__header">
          <div class="title-header">
            <slot name="header"> {{ title }}</slot>
          </div>
          <i v-if="closable" class="dt-modal__close" :class="icon" @click="closeModal"></i>
        </div>
        <!-- body modal  -->
        <div class="dt-modal__body">
            <slot name="body"></slot>
        </div>
        <!-- footer modal  -->
        <div class="dt-modal__footer">
            <slot name="footer"></slot>
        </div>
      </div>
    </div>
  </Teleport>
</template>
<script setup>
const emit = defineEmits(['close', 'open', 'update:modelValue'])
const props = defineProps({
  modelValue: {
    type: Boolean,
    default: false,
  },
  title: {
    type: String,
    default: '',
  },
  closable: { type: Boolean, default: true },
})
props
function closeModal() {
  emit('update:modelValue', false)
  emit('close')
}

</script>
<style>
.dt-modal {
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
  max-height: 90vh;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  width: 640px; /* default */
}
.dt-modal__header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 16px 20px;
  border-bottom: 1px solid #eee;
  gap: 12px;
}
.dt-modal__title {
  font-size: 16px;
  font-weight: 600;
}
.dt-modal__close {
  background: transparent;
  border: none;
  font-size: 20px;
  line-height: 1;
  cursor: pointer;
}
</style>
