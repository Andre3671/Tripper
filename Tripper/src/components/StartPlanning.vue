<script setup>
import { ref } from 'vue'
import WelcomeItem from './WelcomeItem.vue'
import { useRouter } from 'vue-router'
const Stage = ref(1)
const router = useRouter()
const trip = {
  name: ''
}

function sleep(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

function greet() {
  //   alert(`Redirecting to rapport view`)
  // `event` is the native DOM event
  Stage.value = Stage.value + 1
  sleep(2000).then(() => {   router.push({ name: 'trip', query: { id: 213543 } }) });
 
}
</script>

<template>
  <div class="StartWrapper">
    <div id="Headline">
      <h1 style="margin-bottom: 1rem; color: white; font-weight: 600; font-size: 40px;">Tripper</h1>
    </div>
    <div v-if="Stage === 1" id="StartContent">
      <div class="QuestionWindow">
        <div class="QuestionWindowContent" style="height: 100%">
          <v-btn @click="Stage = Stage + 1" style="height: 6rem;" class="button"> Börja Planera </v-btn>
        </div>
      </div>
    </div>
    <div v-if="Stage === 2" class="QuestionWindow">
      <div class="QuestionWindowContent">
        <input v-model="trip.name" />
      </div>
      <div class="QuestionWindowFooter">
        <v-btn @click="Stage = Stage + 1" style="height: 6rem;" class="button"> Nästa steg </v-btn>
      </div>
    </div>
    <div v-if="Stage === 3" class="QuestionWindow">
      <div class="QuestionWindowContent">
        <input v-model="trip.name" />
      </div>
      <div class="QuestionWindowFooter">
        <v-btn @click="Stage = Stage + 1" style="height: 6rem;" class="button"> Nästa steg </v-btn>
      </div>
    </div>
    <div v-if="Stage === 4" class="QuestionWindow">
      <div class="QuestionWindowContent">
        <input v-model="trip.name" />
      </div>
      <div class="QuestionWindowFooter">
        <v-btn @click="Stage = Stage + 1" style="height: 6rem;" class="button"> Nästa steg </v-btn>
      </div>
    </div>
    <div v-if="Stage === 5" class="QuestionWindow">
      <div class="QuestionWindowContent">
        <input v-model="trip.name" />
      </div>
      <div class="QuestionWindowFooter">
        <v-btn @click="greet" style="height: 6rem;" class="button"> Slutför </v-btn>
      
      </div>
    </div>
    <div v-if="Stage === 6" class="QuestionWindow">
      <div class="QuestionWindowContent" style="height: 100%; justify-content: center; display: flex;">
        <v-progress-circular
  color="blue-lighten-3"
  indeterminate
  :size="140"
  :width="11"
></v-progress-circular>
      </div>
    </div>
  </div>
</template>

<style scoped>
.StartWrapper {
  display: flex;
  flex-direction: column;
  width: 45vw;
  height: 80vh;
}

#StartContent {
  height: 80vh;
  width: 100%;
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
