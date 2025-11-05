<script setup>
import DtButton from '@/components/dt-button/DtButton.vue'
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
    <div class="wrap-table d-flex flex-direction-column flex-1 p-24">
      <div class="table-card">
        <!-- header -->
        <div class="table-header d-flex flex-justity-between">
          <!-- left -->
          <div class="toolbar-left"></div>
          <!-- right -->
          <div class="toolbar-right d-flex flex-align-baseline">
            <div class="wrap-search d-flex relative mr-10">
              <div
                class="search-container toolbar-right-search d-flex flex-align-center flex-1 relative"
              >
                <div class="text-edit d-flex">
                  <div class="icon icon-search"></div>
                  <input
                    class="input-cus"
                    type="text"
                    autocomplete="off"
                    style="min-height: 0px"
                    placeholder="Tìm kiếm nhanh trong..."
                    id="a"
                    name="b"
                  />
                </div>
              </div>
            </div>
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
        <div class="table-content flex-1">
          <table class="table">
            <thead>
              <tr>
                <th class="col-select">
                  <input type="checkbox" class="cb" />
                </th>
                <th>Họ và tên</th>
                <th>Số điện thoại</th>
                <th>Email</th>
                <th>Chiến dịch tuyển dụng</th>
                <th>Vị trí tuyển dụng</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>1</td>
                <td>2</td>
                <td>3</td>
                <td>4</td>
                <td>5</td>
                <td>6</td>
              </tr>
              <tr>
                <td>6</td>
                <td>5</td>
                <td>4</td>
                <td>3</td>
                <td>2</td>
                <td>1</td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
              </tr>
            </tbody>
          </table>
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
        <div id="overlay" class="overlay">
          <div class="dialog d-flex flex-direction-column">
            <!-- Header -->
            <div class="dialog__header d-flex flex-justity-between flex-1">
              <div class="dialog__title">Thêm ứng viên</div>
              <button class="icon icon-close" aria-label="Đóng">
                <!-- x icon -->
              </button>
            </div>

            <!-- Main -->
            <div class="dialog__main flex-1">
              <!-- Khu vực -->
              <div class="field">
                <label class="label" for="region">Khu vực</label>
                <div class="control">
                  <select id="region" class="select has-caret">
                    <option value="">Chọn giá trị</option>
                    <option>Miền Bắc</option>
                    <option>Miền Trung</option>
                    <option>Miền Nam</option>
                  </select>
                </div>
              </div>

              <!-- Phone / Email -->
              <div class="form-row cols-2" style="margin-top: 12px">
                <div class="field">
                  <label class="label" for="phone">Số điện thoại</label>
                  <div class="control">
                    <input id="phone" class="input" placeholder="Nhập số điện thoại" />
                  </div>
                </div>
                <div class="field">
                  <label class="label" for="email">Email</label>
                  <div class="control">
                    <input id="email" type="email" class="input" placeholder="Nhập Email" />
                  </div>
                </div>
              </div>

              <!-- Địa chỉ -->
              <div class="field">
                <label class="label" for="addr">Địa chỉ</label>
                <div class="control">
                  <input id="addr" class="input" placeholder="Nhập địa chỉ" />
                </div>
              </div>

              <!-- Học vấn -->
              <div class="section-title">Học vấn</div>

              <div class="kv-subgrid">
                <!-- Trình độ đào tạo -->
                <div class="field">
                  <label class="label" for="degree">Trình độ đào tạo</label>
                  <div class="control">
                    <input id="degree" class="input" placeholder="Nhập trình độ đào tạo" />
                    <div class="right-actions"></div>
                  </div>
                </div>

                <!-- Nơi đào tạo -->
                <div class="field">
                  <label class="label" for="school">Nơi đào tạo</label>
                  <div class="control">
                    <input id="school" class="input" placeholder="Nhập nơi đào tạo" />
                    <div class="right-actions"></div>
                  </div>
                </div>

                <!-- Chuyên ngành -->
                <div class="field">
                  <label class="label" for="major">Chuyên ngành</label>
                  <div class="control">
                    <input id="major" class="input" placeholder="Nhập chuyên ngành" />
                  </div>
                </div>
              </div>

              <!-- Thêm học vấn -->
              <div style="margin-top: 10px">
                <span class="link-add"> Thêm học vấn </span>
              </div>

              <div class="hr"></div>

              <!-- Ngày ứng tuyển + Nguồn ứng viên -->
              <div class="form-row cols-2">
                <div class="field">
                  <label class="label" for="appliedAt"
                    >Ngày ứng tuyển <span class="req">*</span></label
                  >
                  <div class="control">
                    <input id="appliedAt" type="text" class="input" value="2025-10-30" />
                  </div>
                </div>
                <div class="field">
                  <label class="label" for="source">Nguồn ứng viên</label>
                  <div class="control">
                    <select id="source" class="select has-caret">
                      <option value="">Chọn nguồn ứng viên</option>
                      <option>Facebook</option>
                      <option>LinkedIn</option>
                      <option>Giới thiệu</option>
                      <option>Website</option>
                    </select>
                  </div>
                </div>
              </div>

              <!-- (tuỳ chọn) Nhân sự khai thác / Cộng tác viên… có thể thêm các hàng khác ở đây -->
            </div>

            <!-- Footer -->
            <div class="dialog__footer d-flex flex-justity-end flex-1">
              <button class="btn btn-secondary">Hủy</button>
              <button class="btn btn-primary">Lưu</button>
            </div>
          </div>
        </div>
      </div>
    </div>
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
