<template>
  <view class="auth-page">
    <text class="title">注册</text>
    <view class="form">
      <input v-model="username" placeholder="请输入用户名" />
      <input v-model="password" placeholder="请输入密码" password="true" />
      <input v-model="confirmPassword" placeholder="确认密码" password="true" />
      <button @click="handleRegister">注册</button>
    </view>
    <view class="footer">
      <text>已有账号？</text>
      <button @click="goToLogin">前往登录</button>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const username = ref('');
const password = ref('');
const confirmPassword = ref('');

function handleRegister() {
  console.log('注册信息:', { username: username.value, password: password.value, confirmPassword: confirmPassword.value });
  if (password.value !== confirmPassword.value) {
    uni.showToast({ title: '两次密码输入不一致', icon: 'none' });
    return;
  }
  // TODO: Call API
}

function goToLogin() {
  uni.navigateTo({ url: '/pages/auth/login' });
}
</script>

<style scoped>
.auth-page {
  padding: 20px;
}

.title {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
}

.form input {
  display: block;
  width: 100%;
  margin-bottom: 10px;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.form button {
  display: block;
  width: 100%;
  padding: 10px;
  color: #fff;
  background-color: #28a745;
  border: none;
  border-radius: 4px;
  margin-top: 10px;
}

.footer {
  margin-top: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.footer button {
  margin-left: 5px;
  color: #fff;
  background: #28a745;
  padding-left: 10px;
  padding-right: 10px;
  border: none;
  cursor: pointer;
}
</style>
