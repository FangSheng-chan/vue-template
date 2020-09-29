<template>
  <div class="app-container">
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

<!--      <el-table-column label="Author" width="110" align="center">-->
<!--        <template slot-scope="scope">-->
<!--          <span>{{ scope.row.author }}</span>-->
<!--        </template>-->
<!--      </el-table-column>-->
<!--      <el-table-column label="Pageviews" width="110" align="center">-->
<!--        <template slot-scope="scope">-->
<!--          {{ scope.row.pageviews }}-->
<!--        </template>-->
<!--      </el-table-column>-->
<!--      <el-table-column class-name="status-col" label="Status" width="110" align="center">-->
<!--        <template slot-scope="scope">-->
<!--          <el-tag :type="scope.row.status | statusFilter">{{ scope.row.status }}</el-tag>-->
<!--        </template>-->
<!--      </el-table-column>-->
<!--      <el-table-column align="center" prop="created_at" label="Display_time" width="200">-->
<!--        <template slot-scope="scope">-->
<!--          <i class="el-icon-time" />-->
<!--          <span>{{ scope.row.display_time }}</span>-->
<!--        </template>-->
<!--      </el-table-column>-->
    </el-table>
  </div>
</template>

<script>
import { getList } from '@/api/table'

export default {
  data() {
    return {
      list:  [
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
  }
}
</script>
