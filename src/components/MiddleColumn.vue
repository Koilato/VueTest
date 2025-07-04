<template>
  <div class="middle-column" :class="{ collapsed: isMiddleCollapsed }">
    <!-- 中间内容 -->
    <div class="header">
      <h2>参数设置</h2>
    </div>
    <div class="content">
      <div class="section">
        <h3>Skills</h3>
        <div class="item">
          <span class="arrow">></span> Plugins
          <span class="add-button">+</span>
        </div>
      </div>
      <div class="section">
        <h3>Memory</h3>
        <div class="item">
          <span class="arrow">></span> Variables
          <span class="add-button">+</span>
        </div>
        <div class="item">
          <span class="arrow">></span> Database
          <span class="add-button">+</span>
        </div>
        <div class="item">
          <span class="arrow">></span> Long-term memory
          <span class="toggle-switch">On</span>
        </div>
        <div class="item">
          <span class="arrow">></span> Filebox
          <span class="toggle-switch">On</span>
        </div>
      </div>
      <div class="section">
        <h3>Chat experience</h3>
        <div class="item">
          <span class="arrow">></span> Opening questions
        </div>
        <div class="item">
          <span class="arrow">></span> Auto-suggestion
          <span class="toggle-switch">On</span>
        </div>
        <div class="item">
          <span class="arrow">></span> Shortcuts
          <span class="add-button">+</span>
        </div>
        <div class="item">
          <span class="arrow">></span> Voices
          <span class="add-button">+</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const props = defineProps({
  isMiddleCollapsed: Boolean
});
</script>

<style scoped>
.middle-column {
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  padding: 16px;
  background-color: #F7F7FA;
  border-right: 1px solid #e8eaed;
  overflow: hidden;
  flex-basis: var(--middle-column-width); /* Use CSS variable for dynamic width */
}

.middle-column.collapsed {
  padding: 0;
  border-right-width: 0;
}

.middle-column.collapsed > * {
  display: none;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-bottom: 16px;
  border-bottom: 1px solid #e8eaed;
  margin-bottom: 16px;
}

.header h2 {
  margin: 0;
  font-size: 22px; /* 加大字号 */
  font-weight: 600;
  flex-grow: 1;
}

.content {
  flex-grow: 1;
  overflow-y: auto;
}

.section {
  margin-bottom: 24px;
}

.section h3 {
  font-size: 12px;
  color: #5f6368;
  text-transform: none;
  margin-bottom: 8px;
  font-weight: 500;
  padding-left: 8px;
}

.item {
  display: flex;
  align-items: center;
  padding: 8px;
  font-size: 14px;
  cursor: pointer;
  border-radius: 4px;
}

.item:hover {
  background-color: #f1f3f4;
}

.item.selected {
  background-color: #e8eaf6;
  color: #3f51b5;
}

.arrow {
  margin-right: 12px;
  color: #5f6368;
}

.add-button {
  margin-left: auto;
  font-size: 20px;
  font-weight: 400;
  color: #5f6368;
  cursor: pointer;
}

.toggle-switch {
  margin-left: auto;
  background-color: #fff;
  padding: 4px 10px;
  border-radius: 12px;
  font-size: 13px;
  color: #202124;
  border: 1px solid #dadce0;
}
</style>
