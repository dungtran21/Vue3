<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <!--table -->
  <div class="wrap-table d-flex flex-direction-column flex-1 p-24">
    <div class="table-card">
      <!-- header -->
      <div class="table-header d-flex flex-justity-between">
        <!-- left -->
        <div class="toolbar-left"></div>
        <!-- right -->
        <div class="toolbar-right d-flex flex-align-baseline">
          <dt-input-search class="mr-10"> </dt-input-search>
          <div class="item-toolbar mr-10">
            <div class="icon icon-filter"></div>
          </div>
          <div class="item-toolbar mr-10">
            <div class="icon icon-export"></div>
          </div>
          <div class="item-toolbar mr-10">
            <div class="icon icon-setting"></div>
          </div>
          <div class="item-toolbar mr-10">
            <div class="icon icon-interactive"></div>
          </div>
        </div>
      </div>
      <!-- table content -->
      <div class="fixed-table-box">
        <SimpleTable :items="items" :fields="fields" />
      </div>
      <!-- paginator -->
      <div class="pagination d-flex flex-justity-between flex-align-center p-16">
        <div class="pg-left">Tổng: <strong>5367</strong> bản ghi</div>

        <div class="pg-right d-flex flex-align-center gap-2">
          <span class="text-muted">Số bản ghi/trang</span>

          <div class="select-wrap">
            <select class="pg-select">
              <option>10</option>
              <option>25</option>
              <option>50</option>
              <option>100</option>
            </select>
            <span class="select-caret"></span>
          </div>
          <span class="text-muted">1 - 25 bản ghi</span>
          <div class="icon icon-pre"></div>
          <div class="icon icon-next"></div>
        </div>
      </div>
      <!-- dialog -->
    </div>
  </div>
</template>
<script setup>
import DtInputSearch from '@/components/dt-input/DtInputSearch.vue'
import SimpleTable from '@/components/dt-table/DtTable.vue'
import { ref } from 'vue'
const items = ref([
  { id: 1, fullName: 'Nguyễn Văn A', phoneNumber: '0901234567', email: 'a.van.a@example.com', recruitmentCampaign: 'Campaign A', recruitingPosition: 'Frontend Developer', jobs: 'Vue, JavaScript', recruitmentRound: 'Phone screen', appliedAt: '2025-10-01', status: 'New' },
  { id: 2, fullName: 'Trần Thị B', phoneNumber: '0912345678', email: 'tran.thi.b@example.com', recruitmentCampaign: 'Campaign B', recruitingPosition: 'Backend Developer', jobs: 'Node.js, Express', recruitmentRound: 'Interview', appliedAt: '2025-09-28', status: 'Interviewed' },
  { id: 3, fullName: 'Lê Văn C', phoneNumber: '0923456789', email: 'le.van.c@example.com', recruitmentCampaign: 'Campaign A', recruitingPosition: 'Fullstack', jobs: 'Vue, Node.js', recruitmentRound: 'Offer', appliedAt: '2025-09-15', status: 'Offered' },
  { id: 4, fullName: 'Phạm Thị D', phoneNumber: '0934567890', email: 'pham.thi.d@example.com', recruitmentCampaign: 'Campaign C', recruitingPosition: 'QA Engineer', jobs: 'Selenium, Cypress', recruitmentRound: 'Phone screen', appliedAt: '2025-10-03', status: 'New' },
  { id: 5, fullName: 'Hoàng Văn E', phoneNumber: '0945678901', email: 'hoang.van.e@example.com', recruitmentCampaign: 'Campaign B', recruitingPosition: 'Product Manager', jobs: 'Roadmap, Stakeholder', recruitmentRound: 'CV Review', appliedAt: '2025-08-20', status: 'CV Reviewed' },
  { id: 6, fullName: 'Đỗ Thị F', phoneNumber: '0956789012', email: 'do.thi.f@example.com', recruitmentCampaign: 'Campaign A', recruitingPosition: 'UI/UX Designer', jobs: 'Figma, Sketch', recruitmentRound: 'Portfolio', appliedAt: '2025-10-05', status: 'New' },
  { id: 7, fullName: 'Ngô Văn G', phoneNumber: '0967890123', email: 'ngo.van.g@example.com', recruitmentCampaign: 'Campaign D', recruitingPosition: 'DevOps', jobs: 'Docker, Kubernetes', recruitmentRound: 'Interview', appliedAt: '2025-09-01', status: 'Interviewed' },
  { id: 8, fullName: 'Vũ Thị H', phoneNumber: '0978901234', email: 'vu.thi.h@example.com', recruitmentCampaign: 'Campaign C', recruitingPosition: 'Data Engineer', jobs: 'Python, Airflow', recruitmentRound: 'Phone screen', appliedAt: '2025-10-06', status: 'New' },
  { id: 9, fullName: 'Bùi Văn I', phoneNumber: '0989012345', email: 'bui.van.i@example.com', recruitmentCampaign: 'Campaign B', recruitingPosition: 'Business Analyst', jobs: 'SQL, Excel', recruitmentRound: 'CV Review', appliedAt: '2025-07-18', status: 'Rejected' },
  { id: 10, fullName: 'Phan Thị K', phoneNumber: '0990123456', email: 'phan.thi.k@example.com', recruitmentCampaign: 'Campaign A', recruitingPosition: 'Mobile Developer', jobs: 'Flutter, Dart', recruitmentRound: 'Offer', appliedAt: '2025-09-25', status: 'Hired' },
  { id: 11, fullName: 'Trịnh Văn L', phoneNumber: '0909876543', email: 'trinh.van.l@example.com', recruitmentCampaign: 'Campaign E', recruitingPosition: 'Security Engineer', jobs: 'OWASP, PenTest', recruitmentRound: 'Interview', appliedAt: '2025-10-02', status: 'Interviewed' },
  { id: 12, fullName: 'Lý Thị M', phoneNumber: '0918765432', email: 'ly.thi.m@example.com', recruitmentCampaign: 'Campaign D', recruitingPosition: 'HR Specialist', jobs: 'Sourcing, Interviewing', recruitmentRound: 'CV Review', appliedAt: '2025-08-30', status: 'CV Reviewed' }
])

const fields = ref([
  { key: 'fullName', label: 'Họ và tên' },
  { key: 'phoneNumber', label: 'Số điện thoại' },
  { key: 'email', label: 'Email' },
  { key: 'recruitmentCampaign', label: 'Chiến dịch' },
  { key: 'recruitingPosition', label: 'Vị trí tuyển dụng' },
  { key: 'jobs', label: 'Kỹ năng' },
  { key: 'recruitmentRound', label: 'Vòng tuyển' },
  { key: 'appliedAt', label: 'Ngày ứng tuyển' },
  { key: 'status', label: 'Trạng thái' }
])
</script>
<style scoped>
.main-content {
  background-color: rgb(235, 236, 239);
  height: 100%;
}
/* content */
.title {
  font-size: 20px;
  font-weight: 700;
  padding-top: 8px;
  padding-bottom: 4px;
}
.wrap-table {
  box-sizing: border-box;
  min-height: 0; /* IMPORTANT for child overflow */
  height: calc(100% - 50px);
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
.fixed-table-box {
  /* KÍCH THƯỚC CỐ ĐỊNH – tùy bạn đổi px/rem */
  width: 960px;
  height: 420px;

  /* KHÔNG cho flex kéo giãn */
  flex: 0 0 auto;
  align-self: flex-start; /* tránh stretch full chiều ngang cha */

  /* Nội dung thừa thì cuộn */
  overflow: auto;

  /* Không cho lớn/nhỏ hơn kích thước đã set */
  min-width: 960px;
  max-width: 960px;
  min-height: 420px;
  max-height: 420px;

  box-sizing: border-box;
}
</style>
