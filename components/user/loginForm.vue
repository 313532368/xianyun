<template>
  <div class="login">
    <el-form
      ref="userForm"
      :model="userForm"
      :rules="rules2"
      status-icon
      label-width="100px"
      class="demo-ruleForm"
    >
      <el-form-item prop="username">
        <el-input v-model="userForm.username" type="text" placeholder="请输入用户名/手机号" auto-complete="off" />
      </el-form-item>
      <el-form-item prop="password">
        <el-input v-model="userForm.password" type="password" placeholder="请输入密码" auto-complete="off" />
      </el-form-item>

      <el-form-item>
        <el-button @click="submitForm('userForm')" type="primary">
          提交
        </el-button>
        <el-button @click="resetForm('userForm')">
          重置
        </el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      userForm: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    submitForm (userForm) {
      this.$refs[userForm].validate((valid) => {
        if (valid) {
          alert('submit!')
        } else {
        //   console.log('error submit!!')
          return false
        }
      })
    },
    resetForm (userForm) {
      this.$refs[userForm].resetFields()
    }
  }
}
</script>

<style>
</style>
