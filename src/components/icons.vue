<template>

<!-- Cards -->
  <svg
  v-if="iconName === 'Cards'"
    width="28"
    height="28"
    viewBox="0 0 28 28"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <rect width="28" height="28" fill="none" />
    <path
      d="M17 5H11C9.89543 5 9 5.89543 9 7V21C9 22.1046 9.89543 23 11 23H17C18.1046 23 19 22.1046 19 21V7C19 5.89543 18.1046 5 17 5Z"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path d="M11 16H16.5M11 19.5H16.5" :stroke="clicked ? '#76A9FF' : 'black'" />
  </svg>
<!-- Cards -->

<!-- Carousels -->
  <svg
    v-if="iconName === 'Carousels'"
    width="28"
    height="28"
    viewBox="0 0 28 28"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <rect width="28" height="28" fill="none" />
    <path
      d="M17 5H11C9.89543 5 9 5.89543 9 7V21C9 22.1046 9.89543 23 11 23H17C18.1046 23 19 22.1046 19 21V7C19 5.89543 18.1046 5 17 5Z"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path
      d="M20 21V21C21.1046 21 22 20.1046 22 19L22 9C22 7.89543 21.1046 7 20 7V7"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path
      d="M25 12L26.2929 13.2929C26.6834 13.6834 26.6834 14.3166 26.2929 14.7071L25 16"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path
      d="M8 7V7C6.89543 7 6 7.89543 6 9V19C6 20.1046 6.89543 21 8 21V21"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path
      d="M3 16L1.70711 14.7071C1.31658 14.3166 1.31658 13.6834 1.70711 13.2929L3 12"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
  </svg>
  <!-- Carousels -->
</template>

<script>
export default {
  props: {
    iconName: String,
    color: String,
    clicked: Boolean,
  },
};
</script>

<style lang="scss" scoped>
svg {
  margin-top: 7px;
  margin-right: 10px;
  width: 28px;
  height: 28px;
}
</style>
