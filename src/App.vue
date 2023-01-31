<script setup>
import { onMounted } from 'vue'

onMounted(() => { 
  let docu = document.querySelector("h1");
  docu.onmouseover = event =>{
    const letters = "ABCEDFGHIJKLMNOPQRSTUVWXYZ"

    let iterations = 0;
    const interval = setInterval(()=>{
    event.target.innerText = event.target.innerText.split("")
      .map((letter,index)=> {
        if(index < iterations){
          return event.target.dataset.value[index];
        }
        return letters[Math.floor( Math.random() * 26 )]
        })
      .join("");
      if(iterations >= event.target.innerText.length) clearInterval( interval) 
      iterations++;
    },30)

  }
  console.log(docu);
//
})


</script>

<template>
  <h1 data-value="RAYMOND LEWIS"> RAYMOND LEWIS</h1>
</template>

<style>
body{
  background-color:black
}
h1{
  color:white;
  font-size: 5rem;
  font-family: "Space Mono", monospace;
}
</style>
