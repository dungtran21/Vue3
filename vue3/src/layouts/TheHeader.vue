<script setup></script>

<template>
  <div class="header w-100 d-flex flex-justity-between flex-align-center">
    <!-- header left -->
    <div class="header-left d-flex flex-align-center pl-16">
      <div class="header-title-items d-flex flex-align-center">
        <div class="menu">
          <div class="icon-menu"></div>
        </div>
        <!-- logo -->
        <div class="wrap-header ml-16 mr-16">
          <div class="wrap-logo">
            <div class="logo"></div>
          </div>
          <div class="bg-header"></div>
        </div>
        <div class="title-name mr-24">Tuyển Dụng</div>
      </div>
      <!-- search -->
      <div class="wrap-search d-flex relative">
        <div class="search-container d-flex flex-align-baseline flex-1 relative">
          <div class="text-edit d-flex">
            <div class="icon icon-search"></div>
            <input
              class="input-cus"
              type="text"
              autocomplete="off"
              style="min-height: 0px"
              placeholder="Tìm kiếm tin tuyển dụng, ứng viên, nhân tài..."
              id="a"
              name="b"
            />
          </div>
        </div>
      </div>
    </div>
    <!-- header right -->
    <div class="header-right d-flex flex-align-center flex-justity-between">
      <div class="earch-wrap d-flex flex-justity-center mr-24 relative">
        <div class="icon icon-earch mt-3 mr-10 flex-1"></div>
        <div class="icon-text">Website tuyển dụng</div>
      </div>
      <div class="notification-icon-container">
        <div class="icon-notification"></div>
      </div>
      <div class="notification-icon-container">
        <div class="icon-store"></div>
      </div>
      <div class="d-flex flex-justity-center flex-align-center">
        <div class="icon icon-notification-box mr-24"></div>
        <div class="icon icon-support mr-24"></div>
        <div class="icon icon-more mr-24"></div>
        <div class="icon icon-helper mr-24"></div>
        <div></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.header {
  height: 48px;
  background-color: white;
}
.header-left {
  width: auto;
  max-width: 650px;
  flex-grow: 1;
  height: 100%;
  background-color: white;
}
.header-title-items {
  align-items: center;
}
.title-name {
  color: #1f1f1f;
  font-family: Inter;
  font-size: 18px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}
.wrap-header {
  position: relative;
  height: 48px;
}
.menu {
  display: flex;
  z-index: 3;
}
.icon-menu {
  background-image: url("../assets/imgs/icon-swich.svg");
  width: 24px;
  height: 24px;
  min-width: 24px;
}
.bg-header {
  background-image: url("../assets/imgs/header.svg");
  background-position: bottom;
  background-repeat: no-repeat;
  position: absolute;
  z-index: 2;
  inset: 0;
}
.wrap-logo {
  position: relative;
  width: 72px;
  height: 48px;
  left: 22px;
  top: 2px;
  z-index: 1;
}
.logo {
  background-image: url("../assets/imgs/logo.svg");
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
  width: 32px;
  height: 32px;
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
.header-right {
  width: auto;
  height: 100%;
  background-color: white;
}
.earch-wrap {
  top: 4px;
}
.icon-text {
  min-height: 24px;
  padding: 8px 0;
  font-size: 14px;
  color: gray;
}
.notification-icon-container {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  transition: all 0.3s ease;
  cursor: pointer;
  background: transparent;
  margin-right: 12px;
}
.icon-notification {
  background: url("../imgs/icon-notification.svg");
  background-repeat: no-repeat;
  background-size: cover;
  width: 24px;
  height: 24px;
}
.icon-store {
  background: url("../imgs/cs-icon-store.svg");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 20px 20px;
  cursor: pointer;
  height: 20px;
  width: 20px;
}
</style>
