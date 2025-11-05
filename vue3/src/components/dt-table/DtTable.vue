<template>
  <div>
    <table>
      <thead>
        <tr v-for="field in fields" :key="field.key">
          {field.label}
        </tr>
      </thead>
      <tbody>
        <tr v-if="!rows || rows.length === 0">
          <td :colspan="fields.length">Không có dữ liệu</td>
        </tr>
        <tr v-for="row in rows" :key="row.id">
          <td v-for="field in fields" :key="field.key">
            <template v-if="field.type === 'custom'">
              <slot :name="field.key" :row="row" :field="field" :value="row[field.key]">
                {{ row[field.key] }}
              </slot>
            </template>
            <template v-else>
              {{ row[field.key] }}
            </template>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script setup>
const props = defineProps({
  fields: {
    type: Array,
    required: true,
    default: () => [],
  },
  rows: {
    type: Array,
    required: true,
    default: () => [],
  },
})
props
</script>
<style>
</style>
