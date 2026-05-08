<template>
  <div class="login-page">
    <!-- 背景波浪 -->
    <div class="wave-bg">
      <!-- 第4层 最浅 -->
      <svg class="wave wave-4" viewBox="0 0 1440 320" preserveAspectRatio="none">
        <path d="M0,320 L0,200 C240,180 480,220 720,190 C960,160 1200,200 1440,180 L1440,320 Z" fill="#e0e0e0"/>
      </svg>
      <!-- 第3层 -->
      <svg class="wave wave-3" viewBox="0 0 1440 320" preserveAspectRatio="none">
        <path d="M0,320 L0,220 C200,190 400,250 600,210 C800,170 1000,230 1200,200 C1320,180 1380,200 1440,210 L1440,320 Z" fill="#cccccc"/>
      </svg>
      <!-- 第2层 -->
      <svg class="wave wave-2" viewBox="0 0 1440 320" preserveAspectRatio="none">
        <path d="M0,320 L0,240 C300,200 600,260 900,210 C1100,180 1300,220 1440,230 L1440,320 Z" fill="#b8b8b8"/>
      </svg>
      <!-- 第1层 最深最前 -->
      <svg class="wave wave-1" viewBox="0 0 1440 320" preserveAspectRatio="none">
        <path d="M0,320 L0,260 C180,230 360,280 540,250 C720,220 900,260 1080,240 C1260,220 1380,250 1440,260 L1440,320 Z" fill="#a0a0a0"/>
      </svg>
    </div>

    <!-- 登录卡片 -->
    <div class="login-card">
      <!-- 顶部图标 -->
      <div class="logo-wrap">
        <div class="logo-icon">
          <svg width="26" height="26" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="2" y="5" width="15" height="14" rx="2" stroke="white" stroke-width="2" fill="none"/>
            <polygon points="19,9 23,7 23,17 19,15" fill="white"/>
            <circle cx="8.5" cy="12" r="1.5" fill="white"/>
          </svg>
        </div>
      </div>

      <h1 class="title">视频审核平台</h1>
      <p class="subtitle">请输入您的账号和密码登录系统</p>

      <div class="divider"></div>

      <form @submit.prevent="handleLogin" class="login-form">
        <div class="form-item">
          <label class="form-label">账号</label>
          <div class="input-wrap">
            <span class="input-icon">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#bbbbbb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
                <circle cx="12" cy="7" r="4"></circle>
              </svg>
            </span>
            <input
              v-model="form.username"
              type="text"
              placeholder="请输入账号"
              class="form-input"
            />
          </div>
        </div>

        <div class="form-item">
          <label class="form-label">密码</label>
          <div class="input-wrap">
            <span class="input-icon">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#bbbbbb" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect>
                <path d="M7 11V7a5 5 0 0 1 10 0v4"></path>
              </svg>
            </span>
            <input
              v-model="form.password"
              type="password"
              placeholder="请输入密码"
              class="form-input"
            />
          </div>
        </div>

        <button type="submit" class="login-btn">登 录</button>
      </form>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  username: '',
  password: ''
})

const handleLogin = () => {
  console.log('登录信息：', form)
}
</script>

<style scoped>
.login-page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #ffffff;
  position: relative;
  overflow: hidden;
}

/* 背景波浪 */
.wave-bg {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 55%;
  z-index: 0;
  pointer-events: none;
}

.wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.wave-4 {
  height: 65%;
  opacity: 0.35;
}

.wave-3 {
  height: 55%;
  opacity: 0.45;
}

.wave-2 {
  height: 48%;
  opacity: 0.55;
}

.wave-1 {
  height: 42%;
  opacity: 0.7;
}

/* 登录卡片 */
.login-card {
  position: relative;
  z-index: 1;
  width: 440px;
  background: #ffffff;
  border-radius: 12px;
  box-shadow: 0 2px 16px rgba(0, 0, 0, 0.06);
  padding: 44px 44px 36px;
  text-align: center;
}

.logo-wrap {
  display: flex;
  justify-content: center;
  margin-bottom: 18px;
}

.logo-icon {
  width: 52px;
  height: 52px;
  background: #111111;
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.title {
  font-size: 24px;
  font-weight: 700;
  color: #111111;
  margin-bottom: 10px;
  letter-spacing: 2px;
}

.subtitle {
  font-size: 14px;
  color: #999999;
  margin-bottom: 28px;
}

.divider {
  width: 100%;
  height: 1px;
  background: #f0f0f0;
  margin-bottom: 28px;
}

/* 表单 */
.login-form {
  text-align: left;
}

.form-item {
  margin-bottom: 22px;
}

.form-label {
  display: block;
  font-size: 14px;
  color: #111111;
  font-weight: 500;
  margin-bottom: 10px;
}

.input-wrap {
  position: relative;
  display: flex;
  align-items: center;
}

.input-icon {
  position: absolute;
  left: 14px;
  top: 50%;
  transform: translateY(-50%);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
}

.form-input {
  width: 100%;
  height: 44px;
  padding: 0 14px 0 40px;
  border: 1px solid #e8e8e8;
  border-radius: 8px;
  font-size: 14px;
  color: #111111;
  background: #ffffff;
  outline: none;
  transition: border-color 0.2s;
}

.form-input::placeholder {
  color: #bbbbbb;
}

.form-input:focus {
  border-color: #111111;
}

.login-btn {
  width: 100%;
  height: 46px;
  margin-top: 6px;
  background: #111111;
  color: #ffffff;
  border: none;
  border-radius: 8px;
  font-size: 15px;
  font-weight: 500;
  letter-spacing: 6px;
  cursor: pointer;
  transition: opacity 0.2s;
}

.login-btn:hover {
  opacity: 0.85;
}

.login-btn:active {
  opacity: 1;
}
</style>
