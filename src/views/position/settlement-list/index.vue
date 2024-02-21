<!--
 * @Description: 结算列表
 * @Date: 2021-09-10 08:40:19
-->
<template>
  <div>
    <div v-if="showMainPage" class="app-container">
      <div class="form-container">
        <el-form
          ref="form"
          label-width="100px"
          :inline="true"
          :model="form"
          :rules="searchFormRules"
        >
          <el-form-item label="关键词" prop="BiId">
            <el-input ref="BiId" v-model="form.BiId" placeholder="关键词" />
          </el-form-item>
          <el-form-item class="search-button">
            <div class="form-button">
              <el-button type="primary" icon="el-icon-search" @click="onQuery">搜索</el-button>
              <el-button type="primary" icon="el-icon-edit" @click="handle('det')">清空</el-button>
            </div>
          </el-form-item>
        </el-form>
      </div>

      <!-- 表格 -->
      <div v-if="showEmpty === 'table'">
        <el-table
          :key="tableKey"
          :data="list"
          border
          fit
          highlight-current-row
          style="width: 100%;"
          @cell-click="chooseItem"
        >
          <el-table-column v-for="(item,index) in tableList" :key="index" :label="item.label" min-width="110px" align="center">
            <template slot-scope="{row}">
              <span v-if="item.rowName ==='BiTime'">{{ row[item.rowName].split('.')[0] }}</span>
              <span v-else-if="item.rowName==='BiChannel'">{{ row[item.rowName] | dict('BiChannelList') }}</span>
              <span v-else>{{ row[item.rowName] }}</span>
            </template>
          </el-table-column>
        </el-table>
      </div>
      <!-- 分页 -->
      <pagination v-show="total>0" :total="total" :page.sync="form.page" :limit.sync="form.limit" @pagination="getList" />

    </div>

  </div>

</template>

<script>

export default {
  name: 'SettlementList',
  data() {
    return {
      tableKey: 0, // 表格
      arr: [],
      list: null, // 表格
      total: 0, // 分页
      form: {
        // 分页
        page: 1,
        limit: 10,
        OrgId: '',
        OrgName: '',
        DivisionNo: '',
        BiState: '',
        BeginDate: '',
        TransType: '001',
        EndDate: '',
        BiId: '',
        ProdId: '',
        VoucherNo: '',
        BeginAmount: '',
        EndAmount: '',
        DivisionId: ''
        // PayeeAcName: ''
      },
      showEmpty: 'query',
      showMainPage: true,
      temp: {},

      searchFormRules: {
        OrgName: [{ required: true, message: '请选择机构', trigger: 'change' }]

      },
      processVisible: false,

      tableList: [
        // table配置
        { label: '订单编号', rowName: 'BiId' },
        { label: '昵称', rowName: 'LoginId' },
        { label: '建仓时间', rowName: 'CoreCustNo' },
        { label: '持仓类型', rowName: 'PartyNo' },
        { label: '币种', rowName: 'PartyName' },
        { label: '总持仓数量', rowName: 'BiName' },
        { label: '持仓价', rowName: 'ProdCategory' },
        { label: '平仓价', rowName: 'ProdCategory' },
        { label: '杠杆倍数', rowName: 'ProdCategory' },
        { label: '占用保证金', rowName: 'ProdCategory' },
        { label: '止盈率', rowName: 'ProdCategory' },
        { label: '止损率', rowName: 'ProdCategory' },
        { label: '止盈价格', rowName: 'ProdCategory' },
        { label: '止损价格', rowName: 'ProdCategory' },
        { label: '收益', rowName: 'ProdCategory' },
        { label: '手续费', rowName: 'ProdCategory' },
        { label: '是否强平', rowName: 'ProdCategory' }
      ],
      option: {
        placeholder: ' 请输入金额'
      }

    }
  },
  created() {

  },
  methods: {

    getList() {

    },
    clickTens(val) {

    },

    handleResole(res) {

    },
    onQuery() {

    },

    getBranchDialogValue(val) {

    },
    // 选中一行
    chooseItem(row) {

    },
    handle(flag) {

    },
    closeProcess() {
      this.processVisible = false
    },
    getprocessDialogValue(val) {

    },

    // 详情关闭
    closeApproval() {

    }
  }
}
</script>
<style scoped lang="scss">

</style>
