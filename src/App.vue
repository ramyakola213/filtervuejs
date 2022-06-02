

<template>
<div id="app">
   <div class="container">
      <h1> Vuejs Filter Search </h1>
      <form v-on:submit="resetForm">
      <input type="text" name="searchbar" role="seacrh" v-model="input" placeholder="Search from here" /><br>
       <button role="button" type="submit" bname="Reset" >Reset</button>
      </form>
      <div class="item tech" v-for="tech in filteredList()" :key="tech">
         <p>{{ tech }}</p>
      </div>
      <div class="item error" v-if="input&&!filteredList().length">
         <p>No results..</p>
      </div>
    </div>
</div>
</template>

<script setup>
   import { ref } from "vue";
      let input = ref("");
      const technlogies = ["Javascript", "Angular", "Vuejs", "Nodejs","Reactjs","Java","Dotnet"];
      function filteredList() {
          return technlogies.filter((tech) =>
           tech.toLowerCase().includes(input.value.toLowerCase())
          );
       }


</script>

<style>
.container
{
  text-align: center;
  margin: 10% ;
}
h1{
  color: green;
}
input{
  border: 2px solid green;
  padding: 10px 20px;
  margin: 10px;
}
input[type=text]:focus{
  
  outline: none;

}
</style>


