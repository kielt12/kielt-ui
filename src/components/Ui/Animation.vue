<template>
  <!-- <div class="header">
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
  </div> -->
<div>
    <div id="loading-wrapper" >
        
        <div id="loading-content"></div>
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

.header{
  h1{
    font-family: Montserrat;
    font-style: normal;
    font-weight: 300;
    font-size: 28px;
    line-height: 36px;
  }

}



#loading-wrapper{
    position: fixed;
    width: 100%;
  height: 400px;
}


#loading-content {
      width: 100px;
  height: 100px;
  border: 3px solid transparent;
  border-top-color: rgb(121, 61, 185);
  border-bottom-color: rgb(121, 61, 185);
  
  animation: loader 2s linear  infinite;
}

@keyframes loader {
  0% {
 transform: rotate(20deg);
 
  }

  100% {
    transform: rotate(200deg);
    transform: translate(-50%,50%)
  }
}
</style>
