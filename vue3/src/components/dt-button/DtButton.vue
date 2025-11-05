<template>
  <button
    :class="['dt-button', `dt-button--${type}`, { 'is-disabled': disabled }]"
    @click="onClick"
  >
    <i
      v-if="positionIcon !== 'right'"
      class="dt-button__icon dt-button__icon--left"
      :class="icon"
    ></i>
    <span class="dt-button__content">
      <slot></slot>
    </span>
    <i
      v-if="positionIcon !== 'left'"
      class="dt-button__icon dt-button__icon--right"
      :class="icon"
    ></i>
  </button>
</template>
<script setup>
const emit = defineEmits(['click'])
const props = defineProps({
  icon: {
    type: String,
    default: null,
  },
  positionIcon: {
    type: String,
    default: 'left',
    validator: (value) => ['left', 'right'].includes(value),
  },
  type: {
    type: String,
    default: 'primary',
  },
  disabled: {
    type: Boolean,
    default: false,
  },
})
props
function onClick() {
  if (props.disabled) return
  emit('click', props)
}
</script>
<style>
.dt-button {
  display: inline-flex;
  align-items: center;
  padding: 8px 16px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
  transition: all 0.3s ease;
}
.dt-button--primary {
    background: #1677ff;

  color: white;
}
.dt-button--link {
  background: none;
  color: #1976d2;
  padding: 0;
}
.dt-button--warning {
  background-color: #ff9800;
  color: white;
}
.dt-button.error {
  background-color: #f44336;
  color: white;
}
.dt-button__icon {
  display: inline-block;
  align-items: center;
}
.dt-button__content {
  white-space: nowrap;
  overflow: hidden;
}
.dt-button__icon--right {
  margin-left: 8px;
}
.dt-button__icon--left {
  margin-right: 8px;
}
</style>
