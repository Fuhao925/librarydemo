<template>
  <div>
    <el-form ref="elForm" :model="formData" :rules="rules" size="medium" label-width="100px">
      <el-form-item label="类型" prop="field101">
        <el-radio-group v-model="formData.field101" size="medium">
          <el-radio v-for="(item, index) in field101Options" :key="index" :label="item.value"
            :disabled="item.disabled">{{item.label}}</el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item label="图书馆" prop="field102">
        <el-select v-model="formData.field102" placeholder="请选择图书馆" clearable :style="{width: '100%'}">
          <el-option v-for="(item, index) in field102Options" :key="index" :label="item.label"
            :value="item.value" :disabled="item.disabled"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="自习室" prop="field103">
        <el-select v-model="formData.field103" placeholder="请选择自习室" clearable :style="{width: '100%'}">
          <el-option v-for="(item, index) in field103Options" :key="index" :label="item.label"
            :value="item.value" :disabled="item.disabled"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item size="large">
        <el-button type="primary" @click="submitForm">提交</el-button>
        <el-button @click="resetForm">重置</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
  components: {},
  props: [],
  data() {
    return {
      formData: {
        field101: 2,
        field102: undefined,
        field103: undefined,
      },
      rules: {
        field101: [{
          required: true,
          message: '类型不能为空',
          trigger: 'change'
        }],
        field102: [{
          required: true,
          message: '请选择图书馆',
          trigger: 'change'
        }],
        field103: [{
          required: true,
          message: '请选择自习室',
          trigger: 'change'
        }],
      },
      field101Options: [{
        "label": "自习室",
        "value": 1
      }, {
        "label": "研修室",
        "value": 2
      }],
      field102Options: [{
        "label": "主校区",
        "value": 1
      }],
      field103Options: [{
        "label": "选项一",
        "value": 1
      }, {
        "label": "选项二",
        "value": 2
      }],
    }
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {},
  methods: {
    submitForm() {
      this.$refs['elForm'].validate(valid => {
        if (!valid) return
        // TODO 提交表单
      })
    },
    resetForm() {
      this.$refs['elForm'].resetFields()
    },
  }
}

</script>
<style>
</style>
