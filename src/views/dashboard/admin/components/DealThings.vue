<template>
  <el-row :gutter="40" class="deal-things">
    <el-col>
      <div class="pending-thing">
        <div class="text-box">
          <div class="card-panel-description">
            <div class="card-panel-text">
              待处理事物
            </div>
          </div>
        </div>
        <div class="ss">
          <div class="order-left">
            <div class="order-left-1 order-text">
              待处理订单
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              ------------------------------------
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <font color="red">（10）</font>
            </div>
            <div class="order-shipped order-text">
              待发货订单
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              ------------------------------------
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <font color="red">（10）</font>
            </div>
            <div class="delivered-orders order-text">
              已发货订单
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              ------------------------------------
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <font color="red">（10）</font>
            </div>
          </div>
          <div class="order-right">
            <div class="completed-order order-text">
              已完成订单
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              ------------------------------------
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <font color="red">（10）</font>
            </div>
            <div class="out-of-stock order-text">
              新缺货登记
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              ------------------------------------
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <font color="red">（10）</font>
            </div>
            <div class="pending-refund order-text">
              待处理退款
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              ------------------------------------
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              <font color="red">（10）</font>
            </div>
          </div>
        </div>
      </div>
    </el-col>
  </el-row>
</template>

<script>
  export default {
    name: "DealThings",
    components: {}
  }
</script>

<style lang="scss" scoped>
  .dashboard-editor-container {
    padding: 32px;
    background-color: rgb(240, 242, 245);
    position: relative;

    .github-corner {
      position: absolute;
      top: 0px;
      border: 0;
      right: 0;
    }

    .chart-wrapper {
      background: #fff;
      padding: 16px 16px 0;
      margin-bottom: 32px;
    }

    .pending-thing {
      height: 319px;
      background: #fff;
      display: flex;
      flex-direction: column;
    }

    .text-box {
      width: 100%;
      flex: 1;
      background: #ADD8E6;

      .card-panel-description {
        float: left;
        font-weight: bold;
        margin: 26px 26px 26px 0px;


        .card-panel-text {
          line-height: 18px;
          margin-left: 20px;
          font-size: 16px;
          margin-bottom: 12px;
        }
      }

      .card-panel-num {
        font-size: 20px;
      }
    }

    .order-text{
      line-height: 18px;
      color: rgba(0, 0, 0, 0.45);
      font-size: 16px;
      margin-bottom: 12px;
    }

    .ss {
      flex: 5;
      display: flex;

      .order-left {
        margin: 52px 0 0 132px;
        height: 100px;
        flex: 1;
        display: flex;
        flex-direction: column;
        .order-left-1{
          flex: 1;
        }
        .order-shipped{
          flex: 1;
        }
        .delivered-orders{
          flex: 1;
        }
      }

      .order-right {
        margin: 52px 0 0 22px;
        height: 100px;
        flex: 1;
        display: flex;
        flex-direction: column;
        .completed-order{
          flex: 1;
        }
        .out-of-stock{
          flex: 1;
        }
        .pending-refund{
          flex: 1;
        }
      }

    }
  }

  @media (max-width: 1024px) {
    .chart-wrapper {
      padding: 8px;
    }
  }
</style>
