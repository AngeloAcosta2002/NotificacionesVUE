<script setup>
import { ref } from "vue"

let qty = ref (2)

function addValue() {
  qty.value++
  console.log(qty)
}
function subtractvalue() {
  if(qty.value > 0) {
    qty.value--
    console.log(qty)
  }
}
</script>

<template>
  
 <div class="wrapper">
    <div class="profaile">
      <div class="ballon" v-show="qty > 0">{{ qty }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="subtractvalue">-</div>
      <div class="button" @click="addValue">+</div>
    </div>

    <div v-if="qty > 0"> Me escribieron 😊 </div>
    <div v-else> nadie me escribe😭 </div>
 </div>
</template>

<style scoped>
.button{
  width: 32px;
  background-color: #A5A692;
  display: inline-block;
  padding: 4px 0;
  border-radius: 4px;
  margin: 0 8px;
}
.button:hover{
  cursor: pointer;
  background-color: bisque;
}
.button-wrapper{
  text-align: center;
  color: #000000;
  margin-top: 16px;
  margin-bottom: 16px;
  
}
.ballon{
  position: absolute;
  top: 0;
  right: 0;
  width: 32px;
  height: 32px;
  background-color: #F2A71B;
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
.profaile{
  background-image: url("https://shiftart.com/wp-content/uploads/2017/04/RC-Profile-Square.jpg");
  background-size: cover;
  position: relative;
  background-color: orange;
  width: 160px;
  height: 160px;
  border-radius: 100%;
  margin: auto;
}
.wrapper{
  overflow: hidden;
  background-color: #025E73;
  width: 60%;
  border-radius: 12px;
  margin: 0 auto;
}
</style>
