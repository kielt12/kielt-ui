<template>
 <div id="list-complete-demo" class="demo">
  <button @click="shuffle">Shuffle</button>
  <button @click="add">Add</button>
  <button @click="remove">Remove</button>
  <transition-group name="list-complete" tag="p">
    <span
      v-for="item in items"
      :key="item"
      class="list-complete-item"
    >
      {{ item }}
    </span>
  </transition-group>
</div>
</template>

<script>
export default {
    methods: {
    randomIndex: function () {
      return Math.floor(Math.random() * this.items.length)
    },
    add: function () {
      this.items.splice(this.randomIndex(), 0, this.nextNum++)
    },
    remove: function () {
      this.items.splice(this.randomIndex(), 1)
    },
    shuffle: function () {
      this.items.sort(()=> Math.random() - 0.5)
    }
  },
    data(){
        return{
            items: [1,2,3,4,5,6,7,8,9],
    nextNum: 10
        }
    }
}
</script>

<style>
.list-complete-item {
  transition: all 1s;
  display: inline-block;
  margin-right: 10px;
}
.list-complete-enter, .list-complete-leave-to
 {
  opacity: 0;
  transform: translateY(30px);
}
.list-complete-leave-active {
  position: absolute;
}
</style>