<template>
    <div class="main-content d-flex flex-direction-column flex-1">
    <!-- title content -->
    <div class="content-title d-flex flex-justity-between flex-align-baseline">
      <div class="title">Ứng Viên</div>
      <div class="btn-add d-flex flex-align-center gap-2">
        <div class="icon icon-add"></div>
        <div id="addBtn" class="">Thêm ứng viên</div>
      </div>
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