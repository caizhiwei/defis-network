<template>
  <div class="footer">
    <!-- <div class="tip">24H兑换量：23610.17 EOS 4000比订单</div> -->
    <div class="safe">
      <span>{{ $t('public.safeRecord1') }}</span>
      <span class="who" @click="handleToShowReport('slotMist')"> {{ $t('public.safeRecord2') }}</span> &
      <span class="who" @click="handleToShowReport('peckshield')">{{ $t('public.safeRecord4') }} </span>
      <span>{{ $t('public.safeRecord3') }}</span>
    </div>

    <el-dialog
      class="dialog"
      :visible.sync="showImg">
      <img width="100%" src="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh00tvkd0dj30ku112tbw.jpg" />
    </el-dialog>
    <el-dialog
      class="dialog"
      :visible.sync="showImg2">
      <img width="100%" src="@/assets/img/footer/peckshield.jpeg" />
    </el-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showImg: false,
      showImg2: false
    }
  },
  methods: {
    handleToShowReport(name) {
      if (name === 'peckshield') {
        this.showImg2 = true;
        return
      }
      this.showImg = true;
    }
  },
}
</script>

<style lang="scss" scoped>
.dialog{
  /deep/ .el-dialog{
    margin-top: 10vh !important;
    width: 600px;
    .el-dialog__header,
    .el-dialog__body{
      padding: 0;
    }
  }
  img{
    display: block;
  }
}
.footer{
  font-size: 28px;
  margin-top: 30px;
  .safe{
    margin: 12px 0 80px;
    font-size: 24px;
    font-weight: 300;
  }
  .who{
    font-weight: bold;
    color: $color-black;
  }
}
</style>
