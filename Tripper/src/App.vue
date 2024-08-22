<script setup>
import { RouterLink, RouterView } from 'vue-router'


</script>

<template>
  <div class="Wrapper">
    <RouterView />
    <!-- <nav>
      
      <RouterLink to="/about">About</RouterLink>
    </nav> -->
    <v-footer style="display: flex; flex-direction: column; background-color: transparent; margin: 0 auto;">
      <a href="https://www.buymeacoffee.com/andreroygaard" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a></v-footer>
      <p>
        © 2024 André Röygaard. All rights reserved.
      </p>
    </div>
  
</template>

<style scoped>
.Wrapper {
  display: flex;
  justify-content: center;
  text-align: center;
  flex-direction: column;
  align-items: center;
  width: 80vw;
}
</style>
