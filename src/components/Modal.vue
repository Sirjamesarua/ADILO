<script setup>
</script>
<template>
    <div id="myModal" class="modal">

        <!-- Modal content -->
        <div class="modal-content">
            <div class="modal-head">
                <b>New Recording</b>
                <span class="close">&times;</span>
            </div>
            <div class="modal-body">
                <label for="select">Save the recording in</label><br>
                <select name="Select" id="">
                    <option value="New">Select a Project</option>
                </select><br>

                <div class="toggle">
                    <span>Record screen</span>
                    <label class="switch">
                        <input type="checkbox" id="screenCheckbox">
                        <span class="slider round"></span>
                    </label>
                </div>
                <div class="toggle">
                    <span>Record camera</span>
                    <label class="switch">
                        <input type="checkbox" id="cameraCheckbox">
                        <span class="slider round"></span>
                    </label>
                </div>
                <div class="toggle">
                    <span>Record mic</span>
                    <label class="switch">
                        <input type="checkbox" id="micCheckbox">
                        <span class="slider round"></span>
                    </label>
                </div>

                <center><button @click="startRecording">Start Recording</button></center>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Modal',
  methods: {
    async startRecording() {
        var screenCheckbox = document.getElementById("screenCheckbox");
        var cameraCheckbox = document.getElementById("cameraCheckbox");
        var micCheckbox = document.getElementById("micCheckbox");

        sessionStorage.setItem('cameraCheckbox', cameraCheckbox.checked ? 'true' : 'false');
        sessionStorage.setItem('micCheckbox', micCheckbox.checked ? 'true' : 'false');
        window.location = '/record';
    }

  }
}
</script>
