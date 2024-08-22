<script setup>
import { ref } from 'vue'
import { useRouter,useRoute } from 'vue-router'
const Stage = ref(1)
const router = useRouter();
const route = useRoute();
const trip = {
  name: ''
}
// Access the hash value
const hashValue = route.query.id




</script>

<template>
  <div class="StartWrapper">
    <div id="Headline">
      <h1 style="margin-bottom: 1rem; color: white; font-weight: 600; font-size: 40px;">Tripper</h1>
    </div>
    <div  id="StartContent">
      <div class="QuestionWindow">
        <div class="QuestionWindowContent" style="height: 100%">
          <p>{{ hashValue }}</p>
        </div>
      </div>
    </div>

  </div>
</template>

<style scoped>
.StartWrapper {
  display: flex;
  flex-direction: column;

}

#StartContent {
  height: 80vh;
  
  display: block;
  justify-content: center;
  /* align-self: center; */
  align-items: center;
}

.QuestionWindow {
  animation: appear ease-in-out 0.5s forwards;
  background-color: white;
  border-radius: 0.9rem;
  height: 100%;
  width: 100%;
}

.QuestionWindowContent {
  height: 80%;
  display: flex;
  margin: 0 auto;
  align-items: center;
}
.QuestionWindowFooter {
  height: 20%;
  display: flex;
  margin: 0 auto;
  align-items: center;
}

@keyframes appear {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.button {
  margin: 0 auto;
  border-radius: 0.3rem;
  width: 20vw;
  height: 10vh;
  background-color: dodgerblue;
  display: flex;
  justify-content: center;
  /* align-self: center; */
  align-items: center;
}

.button,
a {
  color: whitesmoke;
  font-weight: 500;
  font-size: 2rem;
  text-align: center;
  text-decoration: none;
}

.button:hover {
  background-color: hsla(160, 100%, 37%, 0.5);
}
</style>
