<template>
  <div class="app">
    <div class="content">
  <h1>Color Picker Game</h1>
  <div class="msg">{{ message }}</div>
  </div>
<div class="con">
  <button v-for="color in colors" :key="color" @click="matchColor(color)">
    {{ color }}
  </button>
</div>
  </div>
</template>

<script>
import colorPicker from "../composables/color-picker";


export default {
setup() {
    const { colors, message, matchColor } = colorPicker();
    return { colors, message, matchColor };
    
  },
};
</script>

<style>
body {
 width: 100vw;
height: 100vh;


}
.app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 4em;
}
.con {
  width: 100%;
  height: 40%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 4em;
}
.content{
  font-size: 2em;
align-items: center;
}
.msg {
  font-size: 1.5em;
  margin-top: 1em;
  text-align: center;
}
button {
 width: 20em;
 height: 10em;
 border-radius: 30em;
 font-size: 15px;
 font-family: inherit;
 border: none;
 position: relative;
 overflow: hidden;
 z-index: 1;
 box-shadow: 6px 6px 12px #c5c5c5,
             -6px -6px 12px #ffffff;
}


 
button:hover {
 
 background-image: linear-gradient(to right, #0fd850 0%, #f9f047 100%);
}
</style>
