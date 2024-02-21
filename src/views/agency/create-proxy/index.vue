<!--
 * @Description: 银行交易流水查询
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
          <el-row>
            <el-col :span="12">
              <el-form-item label="代理名称" prop="BiId">
                <el-input ref="BiId" v-model="form.BiId" placeholder="代理名称" />
              </el-form-item>
            </el-col>
            <el-col :span="12">
              <el-form-item label="登录账号" prop="BiId">
                <el-input ref="BiId" v-model="form.BiId" placeholder="登录账号" />
              </el-form-item>
            </el-col>

          </el-row>
          <el-row>
            <el-col :span="12">
              <el-form-item label="初始密码" prop="BiId">
                <el-input ref="BiId" v-model="form.BiId" placeholder="初始密码" />
              </el-form-item>
            </el-col>
            <el-col :span="12">
              <el-form-item label="分佣比例%" prop="BiId">
                <el-input ref="BiId" v-model="form.BiId" placeholder="分佣比例" />
              </el-form-item>
            </el-col>
          </el-row>
        </el-form>
        <div>
          <el-button type="primary" icon="el-icon-edit" @click="handle('det')">保存</el-button>
        </div>
      </div>
    </div>

  </div>

</template>

<script>

export default {
  name: 'CreatedProxy',
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
