<script setup></script>

<template>
  <div class="sidebar h-100 relative">
    <div class="sidebar-list d-flex flex-direction-column gap-4">
      <div class="sidebar-list-item d-flex gap-4">
        <svg class="icon icon-news"></svg>
        <div href="">Tin tuyển dụng</div>
      </div>
      <div class="sidebar-list-item d-flex gap-4">
        <svg class="icon icon-user"></svg>
        <div href="">Ứng viên</div>
      </div>

      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-calender"></svg>
          <div href="">Lịch</div>
        </div>
      </div>
      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-inventory"></svg>
          <div href="">Kho tiềm năng</div>
        </div>
      </div>
      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-marketing"></svg>
          <div href="">Chiến Dịch tuyển dụng</div>
        </div>
      </div>
      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-task"></svg>
          <div href="">Công việc</div>
        </div>
      </div>
      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-ai"></svg>
          <div href="">aiMarketing</div>
        </div>
      </div>
      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-chat"></svg>
          <div href="">Trao đổi với ứng viên</div>
        </div>
      </div>
      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-report"></svg>
          <div href="">Báo cáo</div>
        </div>
      </div>
      <div>
        <div class="sidebar-list-item d-flex gap-4">
          <svg class="icon icon-other"></svg>
          <div href="">Khác</div>
        </div>
      </div>
    </div>
    <div class="collapse d-flex gap-4">
      <svg class="icon icon-back"></svg>
      <div href="">Thu gọn</div>
    </div>
  </div>
</template>

<style scoped>
.sidebar {
  width: 250px;
  background-image: url("../assets/imgs/event-sidebar.svg");
}
.sidebar-list {
  height: 80%;
  margin: 16px;
}
.sidebar-list-item {
  color: gray;
}
.collapse {
  width: 80%;
  position: absolute;
  bottom: 50px;
  left: 10px;
  padding: 8px;
  color: white;
  background-color: rgba(255, 255, 255, 0.3);
}
</style>
