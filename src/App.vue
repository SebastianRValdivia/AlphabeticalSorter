<script >
import {ref} from "vue"

export default {
  setup() {
    const text = ref("Placeholder")

    function order() {
      // Split the text into an array of lines
      const linesArray = text.value.split('\n');

      // Sort the lines alphabetically
      const sortedLines = linesArray.sort();

      // Join the sorted lines back into a single string
      const sortedText = sortedLines.join('\n');

      text.value = sortedText;
    }

    return {
      text,
      order,
    }
  }
}

</script>

<template>
  <div id="main">

    <div class="centered-row">
      <button class="btn" @click="order">Order</button>
    </div>

    <div class="center">
      <textarea class="materialize-textarea" v-model="text" type="text"/>
    </div>


  </div>
</template>

<style>
.bottom-div {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    text-align: center;
}
.center {
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90vh;
    margin: 0;
}
textarea {
    width: 70%; 
    height: 70%; 
    resize: none; 
}
.centered-row {
    display: flex;
    justify-content: center; 
    align-items: center;
}
</style>

