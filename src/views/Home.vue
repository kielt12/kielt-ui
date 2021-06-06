<template>
  <div class="home">
    <div class="drawer">
      <div class="container">
        <h1>UI Componets</h1>
      </div>
      <form class="form">
        <input type="text" placeholder="search" v-model="search" />
      </form>
      <section>
        <ul>
          <li
            class="nav-list"
            v-for="icon in filteredincons"
            :key="icon"
            @click="iconSelector(icon)"
            :style="{
              background: icon.clicked ? 'rgba(118, 169, 255, 0.43)' : '',
            }"
          >
            <div class="nav-item">
              <Icons :iconName="icon.name" :clicked="icon.clicked" />
              <div class="nav-text">
                <h6 :style="{ 'font-weight': icon.clicked ? '700' : '' }">
                  {{ icon.name }}
                </h6>
                <h6 :style="{ color: icon.clicked ? '#76A9FF' : '' }">
                  {{ icon.count }}
                </h6>
              </div>
            </div>
          </li>
        </ul>
      </section>
    </div>
    <div class="container-a">
      <div class="text">
        <picture>
          <a href="https://github.com/kielt12"
            ><img src="../assets/github.png" alt=""
          /></a>
          <a href="https://kielt12.com"
            ><img src="../assets/website.png" alt=""
          /></a>
        </picture>
      </div>
      <div class="component-selector">
        <h1>{{ selected }}</h1>
        <br />
        <component :is="selected"> </component>
      </div>
    </div>
  </div>
</template>

<script>
import { computed, reactive, ref } from "vue";
import Icons from "../components/icons";
import Carousels from "../components/Ui/Carousels.vue"
import Welcome from "../components/Welcome.vue"
import Cards from "@/components/Ui/Card.vue";
export default {
  name: "Home",
  components: {
    Icons,
    Cards,
    Carousels,
    Welcome
  },
  setup() {
    const selected = ref("Welcome");
    const lastClicked = ref(0);
    const search = ref("");
    const icons = reactive([
      {
        id: 0,
        name: "Cards",
        count: 0,
        clicked: false,
      },
      {
        id: 1,
        name: "Carousels",
        count: 0,
        clicked: false,
      },
      {
        id:2,
        name : "Animation",
        count: 0,
        clicked:false
      }
    ]);

    const iconSelector = (icon) => {
      if (icon.id !== selected.value && icon.clicked === false) {
        icon.clicked = icon.clicked ? false : true;
        selected.value = icon.name;
        if (icon.id !== lastClicked.value) {
          icons[lastClicked.value].clicked = false;
          lastClicked.value = icon.id;
        }
      } else {
        selected.value = "Welcome"
        icons[lastClicked.value].clicked = false;
      }
       
    };
    return {
      search,
      selected,
      lastClicked,
      icons,
      iconSelector,
      filteredincons: computed(() =>
        icons.filter((icon) => {
          return icon.name.toLowerCase().match(search.value.toLowerCase());
        })
      ),
    };
  },
};
</script>

<style lang="scss" scoped>
.home {
  display: flex;
}

.drawer {
  width: 273px;

  height: 100vh;

  border-bottom-right-radius: 9px;
  background: #fff;
  text-align: center;
}
.container {
  border-bottom: 1px solid #76a9ff;
  h1 {
    font-family: Kaushan Script;
    font-style: normal;
    font-weight: normal;
    font-size: 24px;
    line-height: 35px;

    color: #76a9ff;
  }
}

.form {
  padding-top: 12px;
  input {
    color: black;
    border-radius: 4px;
    height: 56px;
    width: 215px;
    background: white;
    border: 2px solid #76a9ff;
    &::placeholder {
      position: absolute;
      color: #76a9ff;
    }
  }
}

section {
  cursor: pointer;
  ul {
    padding: 0;
    list-style-type: none;
  }

  li {
    height: 40px;
    margin-left: 2px;

    border-top-right-radius: 99px;
    border-bottom-right-radius: 99px;
  }
}
.nav-list {
  padding-left: 12px;
  padding-right: 12px;
}

.nav-item {
  display: flex;
}

.nav-text {
  width: 100%;
  display: inline-flex;
  justify-content: space-between;
  h6 {
    font-size: 14px;
    font-family: Montserrat;
    font-style: normal;
    font-weight: 500;
    margin-top: 13px;
  }
}
.container-a {
  width: 100%;
}
.text {
  margin-left: 2px;
  background: #fff;
  height: 70px;
  text-align: center;
}
img {
  cursor: pointer;
  padding-top: 18px;
  padding-left: 7px;
  padding-right: 7px;
}
.component-selector {
  text-align: center;
  h1 {
    padding-left: initial;
    font-family: Montserrat;
    font-style: normal;
    font-weight: normal;
    color: #76a9ff;
    font-size: 48px;
    line-height: 36px;
  }
}
</style>
