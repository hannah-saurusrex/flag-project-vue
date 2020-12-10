<template>
  <div class="container header">
    <h1>Where in the world?</h1>
    <button class="btn btn-toggle" id="toggle">
      <i class="far fa-moon"></i>
      <i class="fas fa-moon"></i>
      Dark Mode
    </button>
  </div>
</template>


<script>
export default {
  name: "header",
};
</script>

<style>
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

body.dark .btn-toggle .fas {
  display: inline-block;
}

body.dark .btn-toggle .far {
  display: none;
}
</style>