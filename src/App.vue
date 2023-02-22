<script setup>
import { ref } from "vue";
import MenuItem from './components/MenuItem.vue'
import { RouterLink, RouterView } from "vue-router";

import ChevronUp from "vue-material-design-icons/ChevronUp.vue";
import ChevronDown from "vue-material-design-icons/ChevronDown.vue";
import ChevronLeft from "vue-material-design-icons/ChevronLeft.vue";
import ChevronRight from "vue-material-design-icons/ChevronRight.vue";

let openMenu = ref(false);
</script>

<template>
  <div>
    <div
      class="w-[calc(100%-240px)] h-[60px] fixed right-0 z-20 bg-[#101010] bg-opacity-80 flex items-center justify-between" >
    
      <div class="flex items-center ml-6 ">
      <button type="button" class="rounded-full bg-black p-[1px] cursor-pointer">
        <ChevronLeft fillColor="#ffff" :size="30" />
      </button>
      <button type="button" class="rounded-full bg-black p-[1px] ml-4 cursor-pointer">
        <ChevronRight fillColor="#ffff" :size="30" />
      </button>
    </div>

    <button
    @click="openMenu = !openMenu" :class="openMenu ? 'bg-[#282828]' : 'bg-black'"
    class="bg-black hover:bg-[#282828] transition-all rounded-full p-0.5 mr-8 mt-0.5 cursor-pointer">
      <div class="flex items-center">
        <img src="https://avatars.githubusercontent.com/u/96313603?v=4" class="rounded-full " width="27">
        <div class="text-white text-[14px] ml-1.5 font-semibold ">
          Sahib Huseynov
        </div>

        <ChevronDown v-if="!openMenu" @click="openMenu = true" fillColor="#ffff" :size="25" />
        <ChevronUp v-else @click="openMenu = false" fillColor="#ffff" :size="25" />
      </div>
    </button>
    
    <span 
    v-if="openMenu"
    class="fixed w-[190px] bg-[#282828] shadow-2xl z-50 rounded-sm top-[52px] right-[35px] p-1 cursor-pointer">
      <ul class="text-gray-200 font-semibold text-[14px]">
        <li class="px-3 py-2.5 hover:bg-[#3E3D3D] border-b border-b-gray-600">Profile</li>
        <li class="px-3 py-2.5 hover:bg-[#3E3D3D] border-b border-b-gray-600">Log out</li>

      </ul>
    </span>
  </div>

 <div class="h-full p-6 w-60 z-50 fixed bg-black">
  <RouterLink to="/" >
    <img src="../public/images/icons/spotify-logo.png" width="125">
  </RouterLink>

  <div class="my-8"></div>
  <ul>
    <RouterLink to="/" >
      <MenuItem class="ml-[1px]"  :icon-size="23" name="Home" iconString="home" page-url="/"/>
  </RouterLink>

  <RouterLink to="/search" >
      <MenuItem class="ml-[1px]"  :icon-size="23" name="Search" iconString="search" page-url="/search"/>
  </RouterLink>

  <RouterLink to="/library" >
      <MenuItem class="ml-[1px]"  :icon-size="23" name="Library" iconString="library" page-url="/library"/>
  </RouterLink>

  <div class="py-3.5"></div>
  <MenuItem   :icon-size="24" name="Create PlayList" iconString="playlist" page-url="/playlist"/>
  <MenuItem class="-ml-[1px]"   :icon-size="27" name="Liked Songs" iconString="liked" page-url="/liked"/>
  </ul>

  <div class="border-b border-b-gray-400"></div>
  <ul>
    <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white ">My Playlist #1</li>
    <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white ">My Playlist #2</li>
    <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white ">My Playlist #3</li>
    <li class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white ">My Playlist #4</li>
  </ul>
 </div>
 <div class="fixed right-0 top-0 w-[calc(100%-240px)] overflow-auto  h-full bg-gradient-to-b from-[#1C1C1C] to-black">
  <div class="mt-[70px]"></div>
    <RouterView />
  <div class="mb-[100px]"></div>

 </div>
  </div>
</template>

