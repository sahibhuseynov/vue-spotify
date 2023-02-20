<script setup>
import { ref } from "vue";
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

 <div class="h-full p-6 w-60 z-50 fixed bg-black"></div>
  </div>
</template>

