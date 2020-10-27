<template>
  <div class="app-container">
    <span style="padding-right: 20px"> 模块地址</span>
    <el-select v-model="value" placeholder="请选择">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value">
      </el-option>
    </el-select>
    <span style="padding-left: 20px">通道</span>
    <el-select v-model="value" placeholder="请选择" style="padding-left: 20px">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value">
      </el-option>
    </el-select>
    <div style="display: inline-block;padding-left: 20px">
      <span class="demonstration" style="padding-right: 20px">请选择时间</span>
      <el-date-picker
        v-model="value1"
        type="daterange"
        format="yyyy-MM-dd"
        value-format="yyyy-MM-dd"
        range-separator="至"
        start-placeholder="开始日期"
        end-placeholder="结束日期">{{value1}}
      </el-date-picker>
      <el-button type="primary" @click="clickBtn" style="padding-left: 20px">查询</el-button>
    </div>
    <el-table
      :data="list"
      border
      fit
      highlight-current-row
    >
      <el-table-column align="center" label="序号" width="95">
        <template slot-scope="scope">
          {{ scope.$index+1 }}
        </template>
      </el-table-column>

      <el-table-column label="商品名称">
        <template slot-scope="scope">
          {{ scope.row.name }}
        </template>
      </el-table-column>

      <el-table-column label="商品类型">
        <template slot-scope="scope">
          {{ scope.row.price }}
        </template>
      </el-table-column>

      <el-table-column label="进货价格">
        <template slot-scope="scope">
          {{ scope.row.price }}
        </template>
      </el-table-column>

      <el-table-column label="出售价格">
        <template slot-scope="scope">
          {{ scope.row.salePrice }}
        </template>
      </el-table-column>

      <el-table-column label="进货日期">
        <template slot-scope="scope">
          {{ scope.row.price }}
        </template>
      </el-table-column>

      <el-table-column label="库存量">
        <template slot-scope="scope">
          {{ scope.row.stock }}
        </template>
      </el-table-column>
    </el-table>
    <div class="chart-container">
      <shiyuntu></shiyuntu>
    </div>
  </div>
</template>

<script>
  import {getList} from '@/api/table'
  import Shiyuntu from "@/components/chart/shiyutu";

  export default {
    components: {Shiyuntu},
    data() {
      return {
        list: [
          {
            "id": 1,
            "name": "德芙",
            "images": "1",
            "price": 13,
            "salePrice": 25,
            "typeId": 1,
            "stock": 999,
            "typeName": "巧克力",
            "flag": null,
            "createTime": "2020-09-27T11:36:04.000+0000",
            "updateTime": "2020-09-27T11:36:07.000+0000"
          }
        ],
        options: [{
          value: '选项1',
          label: '通道一'
        }, {
          value: '选项2',
          label: '通道二'
        }, {
          value: '选项3',
          label: '通道三'
        }, {
          value: '选项4',
          label: '通道五'
        }, {
          value: '选项5',
          label: '通道六'
        }],
        value: '',
        value1: '',
      }
    },
    created() {
      this.fetchData()
    },
    methods: {
      fetchData() {
        var vm = this;
        this.axios({
          method: 'GET',
          url: 'http://localhost:8090/product/list'
        }).then(function (response) {
          vm.list = response.data
        })
      },
      clickBtn: function () {
        console.log(this.value1[0]);
        console.log(this.value1[1]);
        console.log(this.value);
      }
    }
  }
</script>
<style scoped>
  .chart-container{
    position: relative;
    width: 100%;
    height: calc(100vh - 84px);
  }
</style>
