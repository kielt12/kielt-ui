<template>
  <div class="header">
    <h1>Array Sort</h1>
  </div>
  <div id="list-complete-demo" class="demo">
    <button @click="shuffle">Shuffle</button>
    <button @click="add">Add</button>
    <button @click="remove">Remove</button>
    <button @click="ascending">Sort</button>
    <transition-group name="list-complete" tag="p">
      <span v-for="item in items" :key="item" class="list-complete-item">
        {{ item }}
      </span>
    </transition-group>
  </div>
  <div class="header">
    <h1>Square Keyframes</h1>
    <div id="square-wrapper">
      <div id="square-content"></div>
    </div>
  </div>
  <div class="header">
    <h1>loading Spinner Keyframes</h1>
    <div id="loading-wrapper">
      <div id ="loading">

      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    randomIndex: function () {
      return Math.floor(Math.random() * this.items.length);
    },
    add: function () {
      this.items.splice(this.randomIndex(), 0, this.nextNum++);
    },
    remove: function () {
      this.items.splice(this.randomIndex(), 1);
    },
    shuffle: function () {
      this.items.sort(() => Math.random() - 0.5);
    },
    ascending: function () {
      this.items.sort((a, b) => a - b);
    },
  },
  data() {
    return {
      items: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      nextNum: 10,
    };
  },
};
</script>

<style lang="scss" scoped>
.list-complete-item {
  transition: all 1s;
  display: inline-block;
  margin-right: 10px;
}
.list-complete-enter,
.list-complete-leave-to {
  opacity: 0;
  transform: translateY(30px);
}
.list-complete-leave-active {
  position: absolute;
}

.header {
  h1 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: 300;
    font-size: 28px;
    line-height: 36px;
  }
}

#square-wrapper {
  position: relative;
  left: 45%;
  height: 200px;
}

#square-content {
  background-color: black;
  width: 100px;
  height: 100px;

  animation: square 2s linear infinite;
}

@keyframes square {
  0% {
    background-color: black;
  }

  25% {
    transform: translateY(100%);
  }

  50% {
    border-radius: 12px;
    background-color: rgb(77, 24, 199);
    transform: translate(100%, 100%);
    //transform: translate(-50%,50%)
  }

  75% {
    border-radius: 50%;
    transform: translate(100%, 0);
  }
}

#loading-wrapper{

}

#loading-content{
  background-color: blue;
  width: 100px;
  height: 100px;
  animation: loading 2s linear infinite;
}

@keyframes loading {
  0%{
    transform: rotate(0);
  }

  100%{
    transform: rotate(360deg);
  }
  
}
#loading,
#loading:before,
#loading:after {
  border-radius: 50%;
  width: 1.5em;
  height: 1.5em;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
  -webkit-animation: loading 1.8s infinite ease-in-out;
  animation: loading 1.8s infinite ease-in-out;
}
#loading {
  color: #0c5a9b;
  font-size: 10px;
  margin: 80px auto;
  position: relative;
  text-indent: -9999em;
  -webkit-transform: translateZ(0);
  -ms-transform: translateZ(0);
  transform: translateZ(0);
  -webkit-animation-delay: -0.16s;
  animation-delay: -0.16s;
}

#loading:before,
#loading:after {
  content: '';
  position: absolute;
  top: 0;
}

#loading:before {
  left: -3.5em;
  -webkit-animation-delay: -0.32s;
  animation-delay: -0.32s;
}

#loading:after {
  left: 3.5em;
}

@-webkit-keyframes loading {
  0%,
  80%,
  100% {
    box-shadow: 0 2.5em 0 -1.3em;
  }
  40% {
    box-shadow: 0 2.5em 0 0;
  }
}
@keyframes loading {
  0%,
  80%,
  100% {
    box-shadow: 0 2.5em 0 -1.3em;
  }
  40% {
    box-shadow: 0 2.5em 0 0;
  }
}

</style>
