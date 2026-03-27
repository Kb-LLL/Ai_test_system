<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script setup>
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', 'Helvetica Neue', Arial, sans-serif;
  background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
  background-attachment: fixed;
  color: #fff;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app {
  min-height: 100vh;
}

::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.5), rgba(118, 75, 162, 0.5));
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.7), rgba(118, 75, 162, 0.7));
}

::selection {
  background: rgba(102, 126, 234, 0.4);
  color: #fff;
}

.el-button {
  transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.el-button:hover {
  transform: translateY(-2px);
}

.el-dialog {
  background: rgba(15, 12, 41, 0.98) !important;
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px !important;
}

.el-dialog__header {
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  padding: 20px 24px !important;
}

.el-dialog__title {
  color: #fff !important;
  font-weight: 600;
}

.el-dialog__body {
  color: rgba(255, 255, 255, 0.85) !important;
  padding: 24px !important;
}

.el-dialog__footer {
  border-top: 1px solid rgba(255, 255, 255, 0.08);
  padding: 16px 24px !important;
}

.el-input__wrapper {
  background: rgba(255, 255, 255, 0.08) !important;
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 12px !important;
  box-shadow: none !important;
}

.el-input__wrapper:hover {
  border-color: rgba(102, 126, 234, 0.5) !important;
}

.el-input__wrapper.is-focus {
  border-color: rgba(102, 126, 234, 0.8) !important;
  box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.15) !important;
}

.el-input__inner {
  color: #fff !important;
}

.el-input__inner::placeholder {
  color: rgba(255, 255, 255, 0.4) !important;
}

.el-form-item__label {
  color: rgba(255, 255, 255, 0.85) !important;
}

.el-form-item__error {
  color: #f56c6c !important;
}

.el-tag {
  border-radius: 8px;
}

.el-message {
  background: rgba(15, 12, 41, 0.95) !important;
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 12px !important;
}

.el-message--success {
  border-color: rgba(67, 233, 123, 0.3) !important;
}

.el-message--error {
  border-color: rgba(245, 108, 108, 0.3) !important;
}

.el-message--warning {
  border-color: rgba(230, 162, 60, 0.3) !important;
}

.el-message--info {
  border-color: rgba(102, 126, 234, 0.3) !important;
}

.el-message__content {
  color: #fff !important;
}

.el-table {
  background: transparent !important;
  border: none !important;
}

.el-table tr {
  background: rgba(255, 255, 255, 0.05) !important;
}

.el-table th {
  background: rgba(102, 126, 234, 0.15) !important;
  color: #fff !important;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08) !important;
}

.el-table td {
  border-bottom: 1px solid rgba(255, 255, 255, 0.05) !important;
  color: rgba(255, 255, 255, 0.85) !important;
}

.el-table--striped .el-table__body tr.el-table__row--striped td {
  background: rgba(255, 255, 255, 0.03) !important;
}

.el-table__empty-text {
  color: rgba(255, 255, 255, 0.4) !important;
}

.el-pagination {
  color: rgba(255, 255, 255, 0.85) !important;
}

.el-pagination button {
  background: rgba(255, 255, 255, 0.08) !important;
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 8px !important;
  color: #fff !important;
}

.el-pagination button:disabled {
  background: rgba(255, 255, 255, 0.03) !important;
}

.el-pager li {
  background: rgba(255, 255, 255, 0.08) !important;
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 8px !important;
  color: rgba(255, 255, 255, 0.85) !important;
}

.el-pager li.is-active {
  background: linear-gradient(135deg, #667eea, #764ba2) !important;
  border-color: transparent !important;
}

.el-card {
  background: rgba(255, 255, 255, 0.08) !important;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 16px !important;
}

.el-card__header {
  border-bottom: 1px solid rgba(255, 255, 255, 0.08) !important;
  color: #fff !important;
}

.el-card__body {
  color: rgba(255, 255, 255, 0.85) !important;
}

.el-select-dropdown {
  background: rgba(15, 12, 41, 0.98) !important;
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 12px !important;
}

.el-select-dropdown__item {
  color: rgba(255, 255, 255, 0.85) !important;
}

.el-select-dropdown__item.hover,
.el-select-dropdown__item:hover {
  background: rgba(102, 126, 234, 0.15) !important;
}

.el-select-dropdown__item.selected {
  color: #667eea !important;
}

.el-textarea__inner {
  background: rgba(255, 255, 255, 0.08) !important;
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 12px !important;
  color: #fff !important;
}

.el-textarea__inner:focus {
  border-color: rgba(102, 126, 234, 0.8) !important;
}
</style> 