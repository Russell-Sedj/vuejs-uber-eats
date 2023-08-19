<template>
  <div class="restaurant--row">
    <h2 class="title">Nos Restaurants</h2>
    <div class="wrapper--card">
      <router-link
        class="restaurant--wrapper"
        v-for="(restaurant, index) in three_restaurant"
        :key="index"
        :to="{ name: 'RestaurantPage', params: { name: restaurant.name } }"
      >
        <RestaurantCard :info_restaurant="restaurant" />
      </router-link>
    </div>
  </div>
</template>

<script>
import RestaurantCard from "./RestaurantCard.vue";

export default {
  name: "RestaurantRow",
  components: {
    RestaurantCard,
  },
  props: {
    three_restaurant: Array,
  },
};
</script>

<style lang="scss" scoped>
.restaurant--row {
  .restaurant--wrapper {
    width: 32%;
    text-decoration: none !important;
  }
  .wrapper--card {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .title {
    font-size: 2rem;
  }
}
</style>
