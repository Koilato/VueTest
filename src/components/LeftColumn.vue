<template>
  <div class="left-column">
    <!-- 左侧内容 -->
    <div class="header">
      <h2>历史会话</h2>
    </div>
    <div class="content">
      <!-- Content can go here -->
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

</script>

<style scoped>
.left-column {
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  padding: 16px;
  background-color: #F7F7FA;
  border-right: 1px solid #e8eaed;
  overflow: hidden;
  flex-basis: var(--left-column-width); /* Use CSS variable for dynamic width */
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

.left-column .content p {
  color: #202124;
  font-size: 14px;
  text-align: left;
}
</style>
