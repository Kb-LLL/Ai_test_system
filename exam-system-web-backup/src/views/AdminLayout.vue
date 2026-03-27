<template>
  <div class="app-container">
    <!-- 左侧菜单 -->
    <div class="sidebar">
      <h3 class="sidebar-title">管理菜单</h3>
      <el-menu
        :default-active="activeMenu"
        class="sidebar-menu"
        @select="handleMenuSelect"
        router
      >
        <!-- 试题管理分组 -->
        <el-submenu index="question">
          <template #title>试题管理</template>
          <el-menu-item index="/admin/question-manage">
            <el-icon><Document /></el-icon>
            <span>题目管理</span>
          </el-menu-item>
          <el-menu-item index="/admin/category-manage">
            <el-icon><Folder /></el-icon>
            <span>类别管理</span>
          </el-menu-item>
        </el-submenu>
        <!-- 考试管理分组 -->
        <el-submenu index="exam">
          <template #title>考试管理</template>
          <el-menu-item index="/admin/paper-manage">
            <el-icon><Files /></el-icon>
            <span>试卷管理</span>
          </el-menu-item>
          <el-menu-item index="/admin/score-manage">
            <el-icon><DataAnalysis /></el-icon>
            <span>成绩管理</span>
          </el-menu-item>
        </el-submenu>
        <!-- 系统管理分组 -->
        <el-submenu index="system">
          <template #title>系统管理</template>
          <el-menu-item index="/admin/banner-manage">
            <el-icon><Picture /></el-icon>
            <span>轮播图管理</span>
          </el-menu-item>
          <el-menu-item index="/admin/notice-manage">
            <el-icon><Bell /></el-icon>
            <span>公告管理</span>
          </el-menu-item>
        </el-submenu>
        <!-- 视频管理分组 -->
        <el-submenu index="video">
          <template #title>视频管理</template>
          <el-menu-item index="/admin/video-manage">
            <el-icon><VideoPlay /></el-icon>
            <span>视频管理</span>
          </el-menu-item>
          <el-menu-item index="/admin/video-category-manage">
            <el-icon><Collection /></el-icon>
            <span>视频分类</span>
          </el-menu-item>
        </el-submenu>
      </el-menu>
    </div>

    <!-- 右侧内容区 -->
    <div class="main-content">
      <router-view />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import { useRoute, useRouter } from 'vue-router'
import { 
  Document, Folder, Files, DataAnalysis, 
  Picture, Bell, VideoPlay, Collection 
} from '@element-plus/icons-vue'

const route = useRoute()
const router = useRouter()

const activeMenu = computed(() => {
  return route.path
})

const handleMenuSelect = (index) => {
  router.push(index)
}
</script>

<style scoped>
.app-container {
  display: flex;
  height: 100vh;
  background: linear-gradient(180deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
}

.sidebar {
  width: 260px;
  background: rgba(15, 12, 41, 0.95);
  backdrop-filter: blur(20px);
  border-right: 1px solid rgba(255, 255, 255, 0.08);
  display: flex;
  flex-direction: column;
  position: relative;
  overflow: hidden;
}

.sidebar::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 20%, rgba(102, 126, 234, 0.15) 0%, transparent 40%),
    radial-gradient(circle at 80% 80%, rgba(118, 75, 162, 0.15) 0%, transparent 40%);
  pointer-events: none;
}

.sidebar-title {
  padding: 24px 20px;
  margin: 0;
  font-size: 1.3rem;
  font-weight: 800;
  color: #fff;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  text-align: center;
  position: relative;
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.2), rgba(118, 75, 162, 0.2));
}

.sidebar-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 3px;
  background: linear-gradient(90deg, #667eea, #764ba2);
  border-radius: 2px;
}

.sidebar-menu {
  border: none;
  background: transparent;
  flex: 1;
  overflow-y: auto;
  padding: 16px 0;
}

.sidebar-menu :deep(.el-submenu__title),
.sidebar-menu :deep(.el-menu-item) {
  color: rgba(255, 255, 255, 0.75);
  font-weight: 500;
  transition: all 0.3s ease;
  border-radius: 12px;
  margin: 4px 12px;
  padding-left: 20px !important;
}

.sidebar-menu :deep(.el-submenu__title:hover),
.sidebar-menu :deep(.el-menu-item:hover) {
  background: rgba(102, 126, 234, 0.15) !important;
  color: #fff;
}

.sidebar-menu :deep(.el-submenu__title) {
  border-radius: 12px;
  margin: 4px 12px;
}

.sidebar-menu :deep(.el-menu-item.is-active) {
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.3), rgba(118, 75, 162, 0.3)) !important;
  color: #fff;
  font-weight: 600;
  position: relative;
}

.sidebar-menu :deep(.el-menu-item.is-active)::before {
  content: '';
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  width: 4px;
  height: 24px;
  background: linear-gradient(180deg, #667eea, #764ba2);
  border-radius: 0 4px 4px 0;
}

.sidebar-menu :deep(.el-submenu .el-menu-item) {
  padding-left: 48px !important;
  font-size: 0.9rem;
}

.sidebar-menu :deep(.el-icon) {
  color: inherit;
  font-size: 18px;
}

.sidebar-menu :deep(.el-menu-item .el-icon),
.sidebar-menu :deep(.el-submenu__title .el-icon) {
  margin-right: 12px;
}

.sidebar-menu :deep(.el-submenu__icon-arrow) {
  color: rgba(255, 255, 255, 0.5);
}

.main-content {
  flex: 1;
  padding: 24px;
  overflow-y: auto;
  background: linear-gradient(135deg, rgba(15, 12, 41, 0.5) 0%, rgba(48, 43, 99, 0.5) 100%);
}

.main-content::-webkit-scrollbar {
  width: 8px;
}

.main-content::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 4px;
}

.main-content::-webkit-scrollbar-thumb {
  background: rgba(102, 126, 234, 0.3);
  border-radius: 4px;
}

.main-content::-webkit-scrollbar-thumb:hover {
  background: rgba(102, 126, 234, 0.5);
}

/* 响应式 */
@media (max-width: 768px) {
  .sidebar {
    width: 200px;
  }
  
  .sidebar-title {
    font-size: 1.1rem;
    padding: 20px 16px;
  }
  
  .sidebar-menu :deep(.el-menu-item),
  .sidebar-menu :deep(.el-submenu__title) {
    padding-left: 16px !important;
    font-size: 0.9rem;
  }
  
  .main-content {
    padding: 16px;
  }
}
</style>
