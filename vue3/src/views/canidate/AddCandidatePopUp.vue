<script></script>
<template>
  <div class="overlay">
    <div >
      <!-- Header -->
      <div class="dialog__header d-flex flex-justity-between">
        <div class="dialog__title">Thêm ứng viên</div>
        <button class="icon icon-close" aria-label="Đóng">
          <!-- x icon -->
        </button>
      </div>

      <!-- Main -->
      <div class="dialog__main">
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
              <div class="right-actions">
                <button class="icon-btn" title="Thêm mới"></button>
                <button class="icon-btn" title="Chọn"></button>
              </div>
            </div>
          </div>

          <!-- Nơi đào tạo -->
          <div class="field">
            <label class="label" for="school">Nơi đào tạo</label>
            <div class="control">
              <input id="school" class="input" placeholder="Nhập nơi đào tạo" />
              <div class="right-actions">
                <button class="icon-btn" title="Thêm mới"></button>
                <button class="icon-btn" title="Chọn"></button>
              </div>
            </div>
          </div>

          <!-- Chuyên ngành -->
          <div class="field">
            <label class="label" for="major">Chuyên ngành</label>
            <div class="control">
              <input id="major" class="input" placeholder="Nhập chuyên ngành" />
              <div class="right-actions">
                <button class="icon-btn" title="Thêm mới"></button>
                <button class="icon-btn" title="Chọn"></button>
              </div>
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
            <label class="label" for="appliedAt">Ngày ứng tuyển <span class="req">*</span></label>
            <div class="control">
              <input id="appliedAt" type="date" class="input" value="2025-10-30" />
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
      <div class="dialog__footer d-flex flex-justity-end">
        <button class="btn btn-secondary">Hủy</button>
        <button class="btn btn-primary">Lưu</button>
      </div>
    </div>
  </div>
</template>
<style scoped>
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
