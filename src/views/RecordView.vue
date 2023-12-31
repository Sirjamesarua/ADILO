<script setup>
import { ref, onMounted } from 'vue';

const micCheckbox = sessionStorage.getItem("micCheckbox");
const cameraCheckbox = sessionStorage.getItem("cameraCheckbox");

const initializeCameraStream = async () => {
  try {
    const stream = await navigator.mediaDevices.getUserMedia({
      video: cameraCheckbox === 'true',
      audio: micCheckbox === 'true',
    });

    const videoContainer = document.getElementById("record-field");
    const videoElement = document.createElement("video");

    videoElement.srcObject = stream;
    videoElement.autoplay = true;
    videoElement.playsinline = true;
    videoElement.style.height = '100%';

    videoContainer.appendChild(videoElement);
  } catch (error) {
    console.error('Error accessing media devices:', error);
    window.alert('Go back and select the required devices.');
  }
};

onMounted(() => {
  initializeCameraStream();
});
</script>

<template>
  <div class="record-container">
    <div><i class="fas fa-record-vinyl"></i> Live Preview</div>
    <div class="record-field" id="record-field"></div>
    <center><button @click="startRecording">Start recording</button></center>
  </div>
</template>

<style>
.record-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.record-field {
  width: 100%;
  background-color: #21455E;
  margin: 10px 0;
  border-radius: 10px;
  position: relative;
  overflow: hidden;
}

video {
  position: absolute;
  top: 0;
  left: 0;
}
</style>
