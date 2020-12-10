<template>
  <div id="app">
    <!-- <section>
      <header></header>
    </section> -->
    <header>
      <div class="container">
        <h1>Where in the world?</h1>
        <button class="btn btn-toggle" id="toggle">
          <i class="far fa-moon"></i>
          <i class="fas fa-moon"></i>
          Dark Mode
        </button>
      </div>
    </header>
    <section>
      <div class="container">
        <input
          class="search"
          id="search"
          type="text"
          placeholder="Search for a country..."
        />

        <div class="dropdown" id="filter">
          Filter by Region
          <i class="fas fa-chevron-down"></i>
          <ul>
            <li>All</li>
            <li>Africa</li>
            <li>Americas</li>
            <li>Asia</li>
            <li>Europe</li>
            <li>Oceania</li>
          </ul>
        </div>
      </div>
    </section>

    <section>
      <div class="container">
        <country-card :countries="countries" />
      </div>
    </section>
  </div>
</template>

<script>
// import Header from "./components/Header.vue";
import CountryCard from "./components/CountryCard.vue";

export default {
  name: "App",
  components: {
    // Header,
    CountryCard,
  },
  data() {
    return {
      countries: [
        {
          id: "united states of america",
          countryName: "USA",
          population: 323947000,
          region: "Americas",
          capitol: "Washington, D.C.",
        },
        {
          id: "Argentina",
          countryName: "Argentina",
          population: 43590400,
          region: "Americas",
          capitol: "Buenos Aires",
        },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;600;800&display=swap");

:root {
  /* (Dark Mode Elements) */
  /* --darkBlue:hsl(209, 23%, 22%); */
  /* (Dark Mode Background) */
  /* --veryDarkBlueBackground: hsl(207, 26%, 17%); */
  /* (Light Mode Text) */
  /* --veryDarkBlueText: hsl(200, 15%, 8%); */
  /* (Light Mode Input) */
  /* --darkGray: hsl(0, 0%, 52%); */
  /* (Light Mode Background) */
  /* --veryLightGray: hsl(0, 0%, 98%); */
  /* (Dark Mode Text & Light Mode Elements) */
  /* --white : hsl(0, 0%, 100%); */
  --background-el: hsl(0, 0%, 100%);
}
* {
  box-sizing: border-box;
}

body {
  background-color: hsl(0, 0%, 98%);
  font-family: "Nunito Sans", sans-serif;
  color: hsl(200, 15%, 8%);
  margin: 0;
}

body.dark {
  background-color: hsl(207, 26%, 17%);
  color: hsl(0, 0%, 100%);
  --background-el: hsl(209, 23%, 22%);
}

body.dark .btn-toggle .fas {
  display: inline-block;
}

body.dark .btn-toggle .far {
  display: none;
}

img {
  max-width: 100%;
}

.header {
  background-color: var(--background-el);
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.12);
}

.container {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: auto;
  padding: 30px;
  position: relative;
}

/* theme button styling */
.btn-toggle {
  background-color: var(--background-el);
  color: inherit;
  font-size: 16px;
  font-weight: 300;
  border: none;
  outline: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 115px;
}

.btn-toggle .fas {
  display: none;
}

/* input styling */
.search {
  background-color: var(--background-el);
  padding: 20px;
  border-radius: 4px;
  border: none;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.12);
  color: inherit;
  min-width: 300px;
  font-size: 14px;
}

.search::placeholder {
  color: inherit;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 300;
  opacity: 0.7;
}

/* dropdown styling */
.dropdown {
  background-color: var(--background-el);
  border-radius: 4px;
  cursor: pointer;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.12);
  font-size: 14px;
  padding: 20px;
  font-weight: 300;
  position: relative;
}

.dropdown .fa-chevron-down {
  margin-left: 10px;
}

.dropdown ul {
  background-color: var(--background-el);
  color: inherit;
  border-radius: 4px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.12);
  display: none;
  padding: 20px;
  width: 100%;
  position: absolute;
  list-style-type: none;
  top: 100%;
  left: 0;
}

.dropdown.open ul {
  display: block;
  z-index: 3;
}

.dropdown ul li {
  margin: 10px 0;
}
</style>
