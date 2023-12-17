<script setup lang="ts">
import {ref} from "vue";
const percentageSpeed = ref()

window.addEventListener("DOMContentLoaded", () => {
  let AudioFile = document.getElementById("AudioTrack")
      let audioPlayer = document.getElementById("Player")
    let sourcePlayer = document.getElementById("SourcePlayer")
  let AudioSpeedButton = document.getElementById("AudioSpeedButton")
  AudioFile.addEventListener("change", (evt) => {
const file = evt.target.files[0]

    if (file) {
      const fileURL = URL.createObjectURL(file);
      sourcePlayer.src = fileURL
      audioPlayer.load();

    }
  })

   AudioSpeedButton.addEventListener("click",  () => {
     audioPlayer.playbackRate = parseFloat(percentageSpeed.value)
     console.log(audioPlayer.playbackRate)
  })
})
</script>

<template>
  <div>
    <input type="file" id="AudioTrack">

    <input type="text" class="" v-model="percentageSpeed">
<audio controls id="Player">
    <source src="" id="SourcePlayer" >
  </audio>
    <input type="button" value="Convert Speed" id="AudioSpeedButton">
  </div>
</template>

<style scoped>

</style>
