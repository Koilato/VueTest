<template>
  <div class="right-column">
    <!-- 右侧内容 -->
    <div class="header">
      <h2>会话</h2>
      <div class="icons">
        <span class="icon"></span>
        <span class="icon settings-icon"></span>
      </div>
    </div>
    <div class="content">
      <!-- More content can go here -->
    </div>
    <div class="footer">
      <div class="input-wrapper">
        <textarea placeholder="发送信息..." class="message-input" ref="messageInput" rows="1" v-model="messageContent"></textarea>
        <img src="../assets/plus.svg" alt="Add" class="add-icon" />
      </div>
      <img src="../assets/up-arrow.svg" alt="Send" class="send-arrow-icon" />
    </div>
  </div>
</template>

<script setup>
import { ref, watch, nextTick } from 'vue';

const messageInput = ref(null);
const messageContent = ref('');

watch(messageContent, () => {
  nextTick(() => {
    if (messageInput.value) {
      messageInput.value.style.height = 'auto';
      messageInput.value.style.height = messageInput.value.scrollHeight + 'px';
    }
  });
});
</script>

<style scoped>
.right-column {
  flex: 1; /* Takes remaining space */
  background-color: #fff;
  position: relative; /* For footer positioning */
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  padding: 16px;
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

.icons {
  display: flex; /* Make icons a flex container */
  align-items: center;
}

.icons .icon {
  display: inline-block;
  width: 24px;
  height: 24px;
  margin-left: 8px;
  background-color: #f1f3f4;
  border-radius: 4px;
  cursor: pointer;
}

.icons .grid-icon {
  /* Basic grid icon */
  background-image: 
    linear-gradient(to right, #5f6368 2px, transparent 2px),
    linear-gradient(to bottom, #5f6368 2px, transparent 2px);
  background-size: 6px 6px;
  background-position: center;
  background-repeat: repeat;
}

.icons .settings-icon {
  /* Basic settings/sliders icon */
  background-image: 
    linear-gradient(to bottom, #5f6368 2px, transparent 2px),
    linear-gradient(to bottom, #5f6368 2px, transparent 2px),
    linear-gradient(to bottom, #5f6368 2px, transparent 2px);
  background-size: 14px 2px;
  background-position: center 4px, center 10px, center 16px;
  background-repeat: no-repeat;
}

.content {
  flex-grow: 1;
  overflow-y: auto;
}

.footer {
  position: absolute;
  bottom: 40px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px 20px 0 20px;
}

.input-wrapper {
  position: relative;
  display: flex;
  align-items: center;
  width: 1000px; /* 设定最大长度为 1000px */
  max-width: calc(100% - 100px); /* 确保在小屏幕上不会超出 */
  border: 2px solid #dadce0;
  border-radius: 24px;
  background-color: #fff;
}

.message-input {
  flex-grow: 1;
  padding: 15px 50px 15px 30px; /* Adjust padding to make text appear lower and make space for plus icon */
  border: none;
  background-color: transparent;
  font-size: 16px;
  font-family: "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "Helvetica Neue", Helvetica, Arial, sans-serif;
  outline: none;
  resize: none;
  overflow-y: auto;
  min-height: 36px;
  max-height: 600px;
  line-height: 1.7;
  letter-spacing: 0.5px;
}

.message-input:focus {
  background-color: transparent;
  border-color: transparent;
}

.add-icon {
  position: absolute;
  right: 15px; /* Position relative to the right edge of the input-wrapper */
  top: 50%;
  transform: translateY(-50%);
  width: 45px;
  height: 45px;
  cursor: pointer;
  border-radius: 50%;

  padding: 6px;
  box-sizing: border-box;

}

.send-arrow-icon {
  width: 55px;
  height: 55px;
  margin-left: 08px;
  cursor: pointer;
  border-radius: 50%;

  padding: 6px;
  box-sizing: border-box;

}
</style>
