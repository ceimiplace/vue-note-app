<script setup></script>
<template>
  <main>
    <div class="module-container">
      <div class="module">
        <textarea
          class="module-text"
          name=""
          id=""
          cols="30"
          rows="10"
        ></textarea>
        <button class="module-button add-button">Add Note</button>
        <button class="module-button close-button">Close</button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1 class="header-heading">Notes</h1>
        <button class="header-button">+</button>
      </header>
      <section class="cards-container">
        <div class="card">
          <p class="card-text">text-text</p>
          <p class="card-date">date-date-</p>
        </div>
        <div class="card">
          <p class="card-text">text-text</p>
          <p class="card-date">date-date-</p>
        </div>
        <div class="card">
          <p class="card-text">text-text</p>
          <p class="card-date">date-date-</p>
        </div>
        <div class="card">
          <p class="card-text">text-text</p>
          <p class="card-date">date-date-</p>
        </div>
        <div class="card">
          <p class="card-text">text-text</p>
          <p class="card-date">date-date-</p>
        </div>
        <div class="card">
          <p class="card-text">text-text</p>
          <p class="card-date">date-date-</p>
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
.module-text {
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
}
.container header {
  display: flex;
  justify-content: space-between;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 0;
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
</style>
