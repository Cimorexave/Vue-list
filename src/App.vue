<template>
  <div id="app">
    <div class="header">
      <div class="check left">
        <input type="checkbox" v-on:change="type1f" />
<svg fill="#fff" xmlns="http://www.w3.org/2000/svg"  viewBox="0 0 16 16" width="16px" height="16px"><path d="M 12.5 1 C 11.125 1 10 2.125 10 3.5 C 10 3.980469 10.144531 4.425781 10.378906 4.808594 L 8.054688 7 L 5.949219 7 C 5.714844 5.863281 4.703125 5 3.5 5 C 2.125 5 1 6.125 1 7.5 C 1 8.875 2.125 10 3.5 10 C 4.703125 10 5.714844 9.136719 5.949219 8 L 8.054688 8 L 10.40625 10.148438 C 10.152344 10.539063 10 11 10 11.5 C 10 12.875 11.125 14 12.5 14 C 13.875 14 15 12.875 15 11.5 C 15 10.125 13.875 9 12.5 9 C 11.984375 9 11.5 9.15625 11.101563 9.429688 L 9 7.507813 L 9 7.476563 L 11.0625 5.539063 C 11.472656 5.824219 11.964844 6 12.5 6 C 13.875 6 15 4.875 15 3.5 C 15 2.125 13.875 1 12.5 1 Z M 12.5 2 C 13.335938 2 14 2.664063 14 3.5 C 14 4.335938 13.335938 5 12.5 5 C 11.664063 5 11 4.335938 11 3.5 C 11 2.664063 11.664063 2 12.5 2 Z M 3.5 6 C 4.335938 6 5 6.664063 5 7.5 C 5 8.335938 4.335938 9 3.5 9 C 2.664063 9 2 8.335938 2 7.5 C 2 6.664063 2.664063 6 3.5 6 Z M 12.5 10 C 13.335938 10 14 10.664063 14 11.5 C 14 12.335938 13.335938 13 12.5 13 C 11.664063 13 11 12.335938 11 11.5 C 11 10.664063 11.664063 10 12.5 10 Z"/></svg>      </div>
      <div class="check centre">
        <input type="checkbox" />
<svg fill="#fff" xmlns="http://www.w3.org/2000/svg"  viewBox="0 0 16 16" width="16px" height="16px"><path d="M 9 2 L 9 3 L 12.292969 3 L 6.023438 9.273438 L 6.726563 9.976563 L 13 3.707031 L 13 7 L 14 7 L 14 2 Z M 4 4 C 2.894531 4 2 4.894531 2 6 L 2 12 C 2 13.105469 2.894531 14 4 14 L 10 14 C 11.105469 14 12 13.105469 12 12 L 12 7 L 11 8 L 11 12 C 11 12.550781 10.550781 13 10 13 L 4 13 C 3.449219 13 3 12.550781 3 12 L 3 6 C 3 5.449219 3.449219 5 4 5 L 8 5 L 9 4 Z"/></svg>
      </div>
      <div class="check rigth">
        <input type="checkbox" v-on:change="type2f" />
        <svg fill="#fff" xmlns="http://www.w3.org/2000/svg"  viewBox="0 0 16 16" width="16px" height="16px"><path d="M 2.5 2 C 1.675781 2 1 2.675781 1 3.5 L 1 11.5 C 1 12.324219 1.675781 13 2.5 13 L 4 13 L 4 15.433594 L 7.652344 13 L 12.5 13 C 13.324219 13 14 12.324219 14 11.5 L 14 3.5 C 14 2.675781 13.324219 2 12.5 2 Z M 2.5 3 L 12.5 3 C 12.78125 3 13 3.21875 13 3.5 L 13 11.5 C 13 11.78125 12.78125 12 12.5 12 L 7.347656 12 L 5 13.566406 L 5 12 L 2.5 12 C 2.21875 12 2 11.78125 2 11.5 L 2 3.5 C 2 3.21875 2.21875 3 2.5 3 Z M 7 4 L 7 5 L 8 5 L 8 4 Z M 7 6 L 7 11 L 8 11 L 8 6 Z"/></svg>
      </div>
    </div>
    <div class="items">
      <div v-if="t1isShowing === true">
      <div v-for="type in type1" v-bind:key="type.id">
        <items v-bind:icon="type.icon"
        v-bind:description="type.description"
        v-bind:number="type.number" />
        </div>
      </div>
    
      <div v-if="t2isShowing === true">
      <div v-for="type in type2" v-bind:key="type.id">
      <items2 v-bind:icon="type.icon"
          v-bind:description="type.description"
          v-bind:number="type.number"
      />
      </div>
      </div>
      <img
        src="https://smilegallerydental.com.au/wp-content/uploads/2019/10/Smile-Gallery-Background-Dark-Purple.jpg"
        alt="background"
      />
    </div>
  </div>
</template>
<script>
import items from "./Items";
import items2 from "./items2";

export default {
  name: "App",
  components: { items , items2 },
  methods: {
    type1f() {
      this.t1isShowing = !this.t1isShowing;
      console.log(this.t1.isShowing);
    },
    type2f() {
      this.t2isShowing = !this.t2isShowing;
      console.log(this.t2isShowing);
    },
  },
  data() {
    return {
      t1isShowing: false,
      t2isShowing: false,
      type1: [
        {
          id: 1,
          icon: "type1",
          description: "box-corners",
          number: 16,
        },
        {
          id: 2,
          icon: "type1",
          description: "box-corners",
          number: 30,
        },
        {
          id: 3,
          icon: "type1",
          description: "box-corners",
          number: 33,
        },
      ],
      type2: [
        {
          icon: "type2",
          description: "bounding box",
          number: 43,
        },
        {
          icon: "type2",
          description: "bounding box",
          number: 44,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
}
.header {
  background-color: rgb(35, 58, 58);
  padding-top: 15px;
  padding-bottom: 15px;
  margin-bottom: 0;
  border-bottom: solid 4px black;
}
.check {
  display: inline;
  margin: 23px;
}
.items {
  background-color: rgb(30, 46, 46);
  margin-top: 0;
}
img {
  position: absolute;
  left: 8px;
  z-index: -1;
  width: 97%;
  height: 100%;
}
</style>
