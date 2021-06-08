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
    <path
      d="M11 16H16.5M11 19.5H16.5"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
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

  <!-- Animation -->
  <svg
    width="28"
    height="28"
    viewBox="0 0 28 28"
    fill="none"
    v-if="iconName === 'Animation'"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      d="M7.1875 7.30769V20H23.8125V7.30769M7.1875 7.30769H6V5H15.5H25V7.30769H23.8125M7.1875 7.30769H23.8125"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path
      d="M20 13.5C20 15.9853 17.9853 18 15.5 18C13.0147 18 11 15.9853 11 13.5C11 11.0147 13.0147 9 15.5 9C17.9853 9 20 11.0147 20 13.5Z"
      :stroke="clicked ? '#76A9FF' : 'black'"
      stroke-width="0.2"
    />
    <path
      d="M15 14.8V12.2C15 12.1176 15.0941 12.0706 15.16 12.12L16.8933 13.42C16.9467 13.46 16.9467 13.54 16.8933 13.58L15.16 14.88C15.0941 14.9294 15 14.8824 15 14.8Z"
      :fill="clicked ? '#76A9FF' : 'black'"
      :stroke="clicked ? '#76A9FF' : 'black'"
      stroke-width="0.4"
    />
    <path
      d="M8 7L9.23077 5H11.6923M11.6923 5L10.4615 7M11.6923 5H14.1538M14.1538 5L12.9231 7M14.1538 5H16.6154M16.6154 5L15.3846 7M16.6154 5H19.0769M19.0769 5L17.8462 7M19.0769 5H21.5385L20.3077 7H22.7692L24 5"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path
      d="M8 22L9.23077 20H11.6923M11.6923 20L10.4615 22M11.6923 20H14.1538M14.1538 20L12.9231 22M14.1538 20H16.6154M16.6154 20L15.3846 22M16.6154 20H19.0769M19.0769 20L17.8462 22M19.0769 20H21.5385L20.3077 22H22.7692L24 20"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path
      d="M6 20H7.1875H23.2188H25V22H7.78125H7.1875H6V20Z"
      :stroke="clicked ? '#76A9FF' : 'black'"
    />
    <path d="M6 7L7 5" :stroke="clicked ? '#76A9FF' : 'black'" />
    <path d="M6 22L7 20" :stroke="clicked ? '#76A9FF' : 'black'" />
  </svg>
  <!-- Animation -->
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
