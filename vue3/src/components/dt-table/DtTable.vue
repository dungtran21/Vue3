<template>
  <div class="table-content">
    <div class="table-scroll" ref="scrollWrap">
      <table
        class="table"
        role="table"
        aria-label="data table"
        :style="tableStyle"
      >
        <caption v-if="!!$slots.caption || caption">
          <slot name="caption">{{ caption }}</slot>
        </caption>

        <colgroup>
          <col
            v-for="field in displayedFields"
            :key="field.key"
            :style="{ width: colWidthPercent, minWidth: colMinWidth + 'px' }"
          />
        </colgroup>

        <thead>
          <tr>
            <th
              v-for="field in displayedFields"
              :key="field.key"
              class="head-cell"
              :title="field.label"
            >
              <slot :name="`head(${field.key})`" :field="field">
                {{ field.label }}
              </slot>
            </th>
          </tr>
        </thead>

        <tbody>
          <tr v-if="!items || items.length === 0" class="empty-row">
            <td :colspan="displayedFields.length" class="dt-table__empty">
              Không có dữ liệu
            </td>
          </tr>

          <tr v-for="(item, rowIndex) in items" :key="item.id ?? rowIndex" class="table-row">
            <template v-for="key in displayedFieldKeys" :key="key">
              <component :is="cellElement(key)">
                <slot
                  :name="`cell(${key})`"
                  :value="format(item, key)"
                  :item="item"
                  :format="(k: string) => format(item, k)"
                >
                  {{ format(item, key) }}
                </slot>
              </component>
            </template>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { computed, PropType, ref } from 'vue'

interface TableField {
  key: string
  label: string
  format?: (v: unknown) => string
  hidden?: boolean
  header?: boolean
}

interface TableItem {
  id?: number | string
  [key: string]: unknown
}

const props = defineProps({
  fields: { type: Array as PropType<TableField[]>, default: () => [] },
  items: { type: Array as PropType<TableItem[]>, default: () => [] },
  caption: { type: String, default: null },
  colMinWidth: { type: Number, default: 140 } // px minimum per column before scroll
})

const displayedFields = computed(() => props.fields.filter((i) => !i.hidden))
const displayedFieldKeys = computed(() => displayedFields.value.map((f) => f.key))

const nCols = computed(() => Math.max(1, displayedFields.value.length))
const colWidthPercent = computed(() => `${(100 / nCols.value).toFixed(6)}%`)
const colMinWidth = props.colMinWidth

// make table have a minimum width equal to nCols * colMinWidth; when container narrower, horizontal scroll appears
const tableStyle = computed(() => {
  return {
    minWidth: `${nCols.value * colMinWidth}px`
  }
})

const cellElement = (key: string) => {
  const field = props.fields.find((f) => f.key === key)
  return field && field.header ? 'th' : 'td'
}

const format = (item: TableItem, key: string) => {
  const field = props.fields.find((f) => f.key === key)
  const val = (item as any)[key]
  return field && field.format ? field.format(val) : (val ?? '')
}
</script>

<style scoped>
.table-content {
  width: 100%;
  box-sizing: border-box;
}

/* scroll wrapper shows horizontal scrollbar when table min-width exceeds container */
.table-scroll {
  width: 100%;
  overflow-x: auto;
  overflow-y: hidden;
}

/* table */
.table {
  width: 100%;
  border-collapse: collapse;
  table-layout: fixed;
  font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  background: #fff;
  box-sizing: border-box;
}

/* header / body cells — equal row height */
.table thead th,
.table tbody td {
  padding: 8px 12px;
  line-height: 1.25;
  vertical-align: middle;
  box-sizing: border-box;
  height: var(--dt-row-height, 44px);
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

/* header */
.table thead th {
  position: sticky;
  top: 0;
  background: linear-gradient(180deg,#fbfdff,#fafafa);
  z-index: 2;
  font-weight: 700;
  font-size: 13px;
  color: #374151;
  border-bottom: 1px solid #e6e9f2;
  text-align: left;
}

/* body */
.table tbody td {
  border-bottom: 1px solid #f0f1f5;
  font-size: 14px;
}

/* empty */
.empty-row td { text-align:center; padding: 28px 16px; color: #6b7280; }

/* hover */
.table-row:hover { background: #fbfcff; }
</style>
