<script setup>
import DtButton from '@/components/dt-button/DtButton.vue'
import { RouterView } from 'vue-router'
</script>

<template>
  <div class="main-content d-flex flex-direction-column flex-1">
    <!-- title content -->
    <div class="content-title d-flex flex-justity-between flex-align-baseline">
      <div class="title">Ứng Viên</div>
      <dt-button type="primary" positionIcon="left" icon="icon icon-add" @click="onAdd">
        Thêm ứng viên
      </dt-button>
    </div>
    <!--table -->
    <RouterView />
  </div>
</template>

<style scoped>
.main-content {
  background-color: rgb(235, 236, 239);
}
/* content */
.title {
  font-size: 20px;
  font-weight: 700;
  padding-top: 8px;
  padding-bottom: 4px;
}
.content-title {
  max-width: 100%;
  padding: 16px 24px 0 24px;
}
.btn-add {
  border: none;
  cursor: pointer;
  padding: 8px 12px;
  border-radius: 6px;
  font-weight: 600;
  background: #1677ff;
  color: #fff;
}
.wrap-table {
}
.table tbody td {
  padding: 12px 16px;
  border-bottom: 1px solid #f0f1f5;
}
.table thead th {
  position: sticky;
  top: 0;
  background: #fafafa;
  z-index: 1;
  text-align: left;
  font-weight: 600;
  font-size: 14px;
  padding: 12px 16px;
  border-bottom: 1px solid #e6e9f2;
  box-sizing: border-box;
}
.table-card {
  background: #fff;
  border-radius: 6px;
}
.toolbar-right-search {
  width: 200px;
  border: 1px solid #e0e6ec;
  background-color: white;
}
.item-toolbar {
  background-color: #ffffff;
  padding: 6px;
  border: 1px solid #e0e6ec;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  cursor: pointer;
}
.tabble-content {
  overflow: auto;
}
.table {
  border: 1px solid #e0e6ec;
  width: 100%;
  height: 100%;
}
.table-header {
  max-width: 100%;
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
  padding: 12px 16px;
}
.pagination {
  max-width: 100%;
  background-color: #f5f5f5;
}
/* pop-up */
.overlay {
  height: 100%;
  min-height: 0px;
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.35);
  display: none;
  justify-content: center;
  align-items: flex-start;
  z-index: 999;
}
.overlay.open {
  display: flex;
  align-items: center;
}
.dialog {
  background-color: white;
  width: 500px;
  max-height: 90%;
  padding: 16px;
}
.dialog__main {
  overflow: scroll;
}
.field {
  margin-top: 12px;
}
.control {
  display: flex;
  justify-content: baseline;
  height: 32px;
  border: 1px solid #dddde4;
}
.control:hover {
  border: 1px solid #2970f6;
}
.control:focus :focus-within {
  border: 1px solid #2970f6;
}
input {
  border: none;
  width: 100%;
  max-width: 80%;
  overflow: hidden;
  outline: none;
}
select {
  border: none;
  width: 100%;
  overflow: hidden;
  outline: none;
}
.dialog__footer {
  background-color: rgb(241, 242, 245);
}
.btn {
  height: 38px;
  border-radius: 8px;
  padding: 0 16px;
  font-weight: 600;
  border: 1px solid transparent;
  cursor: pointer;
}
.btn-secondary {
  background: #f3f4f6;
  color: #111827;
  border-color: #e5e7eb;
}

.btn-primary {
  background: #2563eb;
  color: #fff;
}
</style>
