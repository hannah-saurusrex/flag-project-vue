<template>
  <section>
    <div v-for="country in countries" :key="country.id">
      <div>
        <img src="" alt="" />
      </div>

      <div class="card-body">
        <h3>{{ country.name }}</h3>
        <p>
          <strong>Population: </strong>
          {{ country.population }}
        </p>
        <p class="country-region">
          <strong>Region: </strong>
          {{ country.region }}
        </p>
        <p>
          <strong>Capitol: </strong>
          {{ country.capitol }}
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "country-card",
  props: {
    countries: Array,
  },
};
</script>

<style scoped>
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
</style>