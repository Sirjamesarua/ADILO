<script setup>
import Modal from '../components/Modal.vue'
import Recordings from '../../data.json'
</script>

<template>
  <section class="main-body-container">
    <section class="sidebar-container">
        <button id="active"><i class="fas fa-film"></i>My Recordings</button>
        <button><i class="fas fa-share-alt"></i>Requested</button>
    </section>
    <section class="mainbar-container">
        <div><small>Snapbyte > My Recordings</small></div>
        <div class="filter-container">
            <span><b>My Recordings 25</b></span> 
            <div class="filters">
                <button class="filterbtn"><i class="fas fa-sort"></i>By Date</button>
                <button class="filterbtn"><i class="fas fa-filter"></i>Add Filter</button>
                <button class="bluebtn"><i class="fas fa-video"></i>New Request</button>
                <button class="redbtn" @click="openModal"><i class="fas fa-record-vinyl"></i>Start Recording</button>
            </div>
        </div>
        <div class="recordings-table">
          <table>
            <tr>
              <th class="video">Recordings</th>
              <th>Title</th>
              <th>Views</th>
              <th>Size</th>
              <th>Last Modified</th>
            </tr>
            <tr v-for="recording in Recordings" :key="recording.id">
              <td><img :src="recording.thumbnail" width="200px" height="100px" alt=""></td>
              <td>
                <h4>{{ recording.title }}</h4>
                <small>{{ recording.description }}</small>
              </td>
              <td><small>{{ recording.views }}</small></td>
              <td><small>{{ recording.size }}</small></td>
              <td><small>{{ recording.lastModified }}</small></td>
              <td><i class="fas fa-ellipsis-h"></i></td>
            </tr>
          </table>
            <!-- <table>
                <tr>
                  <th class="video">Recordings</th>
                  <th>Title</th>
                  <th>Views</th>
                  <th>Size</th>
                  <th>Last Modified</th>
                </tr>
                <tr>
                  <td><img src="@/assets/videos/video.jpg" width="200px" height="100px" alt=""></td>
                  <td><h4>Getting it right the first time</h4><small>This videos is a descrition on how to make money easily Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi, praesentium?</small></td>
                  <td><small>324</small></td>
                  <td><small>923 KB</small></td>
                  <td><small>3 months ago</small></td>
                  <td><i class="fas fa-ellipsis-h"></i></td>
                </tr>
                <tr>
                    <td><img src="@/assets/videos/video.jpg" width="200px" height="100px" alt=""></td>
                    <td><h4>Getting it right the first time</h4><small>This videos is a descrition on how to make money easily Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi, praesentium?</small></td>
                  <td>324</td>
                  <td><small>923 KB</small></td>
                  <td><small>3 months ago</small></td>
                  <td><i class="fas fa-ellipsis-h"></i></td>
                </tr>
                <tr>
                    <td><img src="@/assets/videos/video.jpg" width="200px" height="100px" alt=""></td>
                    <td><h4>Getting it right the first time</h4><small>This videos is a descrition on how to make money easily Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi, praesentium?</small></td>
                  <td>324</td>
                  <td><small>923 KB</small></td>
                  <td><small>3 months ago</small></td>
                  <td><i class="fas fa-ellipsis-h"></i></td>
                </tr>
                <tr>
                    <td><img src="@/assets/videos/video.jpg" width="200px" height="100px" alt=""></td>
                    <td><h4>Getting it right the first time</h4><small>This videos is a descrition on how to make money easily Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi, praesentium?</small></td>
                  <td>324</td>
                  <td><small>923 KB</small></td>
                  <td><small>3 months ago</small></td>
                  <td><i class="fas fa-ellipsis-h"></i></td>
                </tr>
                <tr>
                    <td><img src="@/assets/videos/video.jpg" width="200px" height="100px" alt=""></td>
                    <td><h4>Getting it right the first time</h4><small>This videos is a descrition on how to make money easily Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi, praesentium?</small></td>
                  <td>324</td>
                  <td><small>923 KB</small></td>
                  <td><small>3 months ago</small></td>
                  <td><i class="fas fa-ellipsis-h"></i></td>
                </tr>
            </table> -->
        </div>
    </section>
</section>

<Modal />
</template>
<script>
export default {
  name: 'HomeView',
  methods: {
    openModal() {
      var modal = document.getElementById("myModal");
      var span = document.getElementsByClassName("close")[0];
      console.log('yes');
      modal.style.display = "block";

      span.onclick = function() {
        modal.style.display = "none";
      };

      window.onclick = function(event) {
        if (event.target == modal) {
          modal.style.display = "none";
        }
      };
    },
    
  }
}
</script>
