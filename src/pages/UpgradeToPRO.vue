<template>
  <div class="content">
    <div class="md-layout">
      <div class="md-layout-item md-size-100 mx-auto md-small-size-100">
        <md-card>
          <md-card-header data-background-color="purple">
            <h4 class="title">Laporan Keuangan Sumbangan Pembinaan Pendidikan (SPP)</h4>
            <p class="category">Rincian biaya keluar - masuk</p>
          </md-card-header>

          <md-card-content>
            <div class="table-responsive table-upgrade">
              <table class="table" cellspacing="0">
                <thead>
                  <tr>
                    <th class="text-center">Tanggal</th>
                    <th class="text-center">Penanggung Jawab</th>
                    <th class="text-center">Keterangan</th>
                    <th class="text-center">Dana Masuk(Rp.)</th>
                    <th class="text-center">Dana Keluar(Rp.)</th>
                    <th class="text-center">Status</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td class="text-center">02-05-2024</td>
                    <td class="text-center">Rin</td>
                    <td class="text-center">Renovasi Kelas</td>
                    <td class="text-center">60</td>
                    <td class="text-center">200</td>
                    <td class="text-center"><i class="fa fa-times text-danger"></i></td>
                  </tr>
                  <tr>
                    <td class="text-center">02-05-2024</td>
                    <td class="text-center">Plugins</td>
                    <td class="text-center">Lomba 17an</td>
                    <td class="text-center">2</td>
                    <td class="text-center">15</td>
                    <td class="text-center"><i class="fa fa-check text-success"></i></td>
                  </tr>
                  <tr>
                    <td class="text-center">02-05-2024</td>
                    <td class="text-center">Plugins</td>
                    <td class="text-center">Example Pages</td>
                    <td class="text-center">3</td>
                    <td class="text-center">27</td>
                  </tr>
                  <tr>
                    <td class="text-center">02-05-2024</td>
                    <td class="text-center">Plugins</td>
                    <td class="text-center">Plugins</td>
                    <td class="text-center">
                      <i class="fa fa-times text-danger"></i>
                    </td>
                    <td class="text-center">
                      <i class="fa fa-check text-success"></i>
                    </td>
                  </tr>
                  <tr>
                    <td class="text-center">DataTable</td>
                    <td class="text-center"><i class="fa fa-times text-danger"></i></td>
                    <td class="text-center">
                      <i class="fa fa-check text-success"></i>
                    </td>
                  </tr>
                  <tr>
                    <td class="text-center">Mini Sidebar</td>
                    <td class="text-center">
                      <i class="fa fa-times text-danger"></i>
                    </td>
                    <td class="text-center">
                      <i class="fa fa-check text-success"></i>
                    </td>
                  </tr>
                  <tr>
                    <td>Premium Support</td>
                    <td class="text-center">
                      <i class="fa fa-times text-danger"></i>
                    </td>
                    <td class="text-center">
                      <i class="fa fa-check text-success"></i>
                    </td>
                  </tr>
                </tbody>
              </table>
              <md-button
                target="_blank"
                style="float: right"
                href="https://www.creative-tim.com/product/vue-material-dashboard-pro/?ref=vue-md-free-upgrade-live"
                class="md-info md-round"
                >Upgrade to PRO</md-button
              >
            </div>
          </md-card-content>
        </md-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.mx-auto {
  margin-left: auto !important;
  margin-right: auto !important;
}

.md-card {
  margin-top: 50px;
}

.table-responsive {
  overflow: auto;
}

.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 1rem;
  background-color: transparent;

  thead tr th {
    font-size: 1.063rem;
    border-top-width: 0;
    font-weight: 300;
    border-bottom: 1px solid rgba(0, 0, 0, 0.06);
  }

  & > tbody > tr > td,
  & > tbody > tr > th,
  & > tfoot > tr > td,
  & > tfoot > tr > th,
  & > thead > tr > td,
  & > thead > tr > th {
    padding: 12px 8px;
    vertical-align: middle;
  }

  & > tbody > tr {
    position: relative;
  }

  td,
  th {
    padding: 0.75rem;
    vertical-align: top;
    border-top: 1px solid rgba(0, 0, 0, 0.06);
  }
}
</style>
