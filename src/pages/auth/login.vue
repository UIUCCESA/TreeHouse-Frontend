<template>
  <view class="auth-page">
    <text class="title">登录</text>
    <view class="form">
      <input v-model="username" placeholder="请输入用户名" />
      <input v-model="password" placeholder="请输入密码" password="true" />
      <button @click="handleLogin">登录</button>
    </view>
    <view class="footer">
      <text>没有账号？</text>
      <button @click="goToRegister">前往注册</button>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const username = ref('');
const password = ref('');

function handleLogin() {
  console.log('登录信息:', { username: username.value, password: password.value });
  // TODO: API
}

function goToRegister() {
  uni.navigateTo({ url: '/pages/auth/register' });
}
</script>

<style scoped>
.auth-page {
  padding: 30px;
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
  background-color: #007bff;
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
  background: #007bff;
  border: none;
  padding-left: 10px;
  padding-right: 10px;
  cursor: pointer;
}
</style>
