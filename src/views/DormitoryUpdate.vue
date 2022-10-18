<template>
    <!--  修改宿舍-->
    <div style="margin-top: 60px;margin-left:330px;width: 300px;height: 500px;border: 0 solid red;">
      <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
        <el-form-item label="ID">
          <el-input v-model="ruleForm.id"></el-input>
        </el-form-item>
        <el-form-item label="名称" prop="name">
          <el-input v-model="ruleForm.name"></el-input>
        </el-form-item>
        <el-form-item label="联系电话" prop="telephone">
          <el-input v-model="ruleForm.telephone"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('ruleForm')">立即修改</el-button>
          <el-button @click="resetForm('ruleForm')">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  
  </template>
  
  <script>
  export default {
    data() {
      return {
        category: null,
        ruleForm: {
          id: '',
          buildingId: '',
          name: '',
          type: '',
          telephone: ''
        },
        rules: {
          buildingId: [
            {required: true, message: '请选择楼栋', trigger: 'change'}
          ],
          name: [
            {required: true, message: '请输入名称', trigger: 'blur'}
          ],
          telephone: [
            {required: true, message: '请输入联系电话', trigger: 'blur'}
          ],
          type: [
            {required: true, message: '请选择房间类型', trigger: 'change'}
          ]
        }
      };
    },
    methods: {
      
    },
    created() {
      
    }
  }
  </script>
  