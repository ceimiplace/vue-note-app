<script setup>
import { ref } from "vue";
const showModal = ref(false);
const note = ref("");
const notes = ref([]);
const showModalError = ref(false);
function getRandomColor() {
  return "hsl(" + Math.random() * 360 + ", 100%, 75%)";
}
function addNote() {
  if (note.value.length < 10) {
    showModalError.value = true;
    return;
  }
  notes.value.push({
    text: note.value,
    date: new Date(),
    id: Math.floor(Math.random() * 1000),
    color: getRandomColor(),
  });
  note.value = "";
  showModal.value = false;
}
</script>
<template>
  <main>
    <div v-if="showModal" class="module-container">
      <div class="module">
        <textarea
          v-model.trim="note"
          class="module-text"
          name=""
          id=""
          cols="30"
          rows="10"
        ></textarea>
        <p class="module-error" v-if="showModalError">
          Please enter at least 10 valid characters
        </p>
        <button class="module-button add-button" @click="addNote">
          Add Note
        </button>
        <button class="module-button close-button" @click="showModal = false">
          Close
        </button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1 class="header-heading">Notes</h1>
        <button class="header-button" @click="showModal = true">+</button>
      </header>
      <section class="cards-container">
        <div
          class="card"
          v-for="userNote in notes"
          :style="{ backgroundColor: userNote.color }"
          :id="userNote.id"
        >
          <p class="card-text">{{ userNote.text }}</p>
          <p class="card-date">
            {{ userNote.date.getDate() }}/{{ userNote.date.getMonth() + 1 }} /
            {{ userNote.date.getFullYear() }}
          </p>
        </div>
      </section>
    </div>
  </main>
</template>
<style scoped>
main {
  width: 100vw;
  height: 100vh;
  position: relative;
}
.module-container {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.574);
  z-index: 2;
}
.module {
  background-color: white;
  display: flex;
  width: 600px;

  flex-direction: column;
  padding: 30px;
}

.module-button {
  padding: 10px;
  border: none;
  font-size: 16px;
  font-weight: bold;
  color: white;
  cursor: pointer;
}
.add-button {
  background-color: blueviolet;
  margin-top: 10px;
}
.close-button {
  background-color: red;
  margin-top: 10px;
}
.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;
}
.container header {
  display: flex;
  justify-content: space-between;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 10px 20px;
}
.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 200px;
  min-height: 200px;
  background-color: aliceblue;
  border-radius: 10px;
  padding: 10px;
}
.header-heading {
  font-size: 40px;
  font-weight: bold;
}
.header-button {
  background-color: black;
  color: white;
  border-radius: 50%;

  width: 40px;
  height: 40px;
  border: none;
  cursor: pointer;
}
.module-error {
  color: red;
}
</style>
