<template>
  <div id="app">
    <button class="toggle-btn" @click="toggleSidebar">{{ sidebarOpen ? '收起' : '展开' }}侧边栏</button>

    <div
      class="sidebar"
      :class="{ 'sidebar-open': sidebarOpen, 'sidebar-closed': !sidebarOpen }">
      <h2>侧边栏内容</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sidebarOpen: true
    };
  },
  methods: {
    toggleSidebar() {
      this.sidebarOpen = !this.sidebarOpen;
    }
  }
};
</script>

<style scoped>
#app {
  display: flex;
  height: 100vh;
}

.toggle-btn {
  position: absolute;
  top: 20px;
  left: 20px;
  padding: 10px;
  font-size: 16px;
  background-color: #008CBA;
  color: white;
  border: none;
  cursor: pointer;
  z-index: 10;
}

.sidebar {
  position: fixed;
  top: 0;
  left: 0;
  width: 250px;
  height: 100%;
  background-color: #333;
  color: white;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.sidebar-open {
  transform: translateX(0);
}

.sidebar-closed {
  transform: translateX(-100%);
}

</style>
