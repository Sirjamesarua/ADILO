<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header> -->
  <nav>
    <div class="logo"><RouterLink to="/" class="logo"><img width="48" height="48" src="https://img.icons8.com/color/48/spoon-logo.png" alt="spoon-logo"/>Adilo</RouterLink></div>

    <div class="menu">
        <div class="menu-list">
            <a href="#">Projects</a>
            <span class="dropdown">
                <a href="#" id="active" class="dropbtn">Tools & App <small><i class="fas fa-chevron-down"></i></small></a>
                <div class="dropdown-content">
                    <a href="#">Snapbyte Recorder</a>
                    <hr>
                    <a href="#">AudioBounce</a>
                    <hr>
                    <a href="#">Sugar Voice</a>
                  </div>
            </span>
            <a href="#">Channels</a>
            <a href="#">Contacts</a>
            <a href="#">Analytics</a>
            <a href="#">Settings</a>
        </div>
    </div>
    
    <div class="profile">
        <div class="help">Help</div>
        <div class="hr"></div>
        <div class="main-profile">
            <i class="fas    fa-user-tie fa-2x avatar"></i>
            <div class="profile-text">
                <div class="name"><b>James Arua</b></div>
                <div class="email">dev.sirjames@gmail.com</div>
            </div>
        </div>
    </div>

    <div class="nav-bar"><i class="fas fa-bars"></i></div>
    
</nav>

  <RouterView />
</template>
