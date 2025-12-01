<template>
  <div class="card">
    <h2>Message: {{ message }}</h2>
    <h2>Number: {{ number }}</h2>
    <button @click="changeMessageToUpperCase">
      Change message to upper case
    </button>
    <button @click="incrementNumber">Increment number</button>
  </div>
  <div class="card">
    <h2>Name: {{ wizard.name }}</h2>
    <h2>Wand: {{ wizard.wand }}</h2>
    <button @click="changeNameToUpperCase">Change name to upper case</button>
    <button @click="changeWandCore">Change wand core</button>
    <button @click="changeWizard">Change wizard</button>
  </div>
  <div class="card">
    <h2>Array: {{ wizards }}</h2>
    <button @click="wizards.push({id: 1004, name: 'Harry Potter', house: 'Gryffindor', age: 15})">Add a new wizard</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

let message = ref('Hello, Reactivity!');
let number = ref(1);

function changeMessageToUpperCase() {
  message.value = message.value.toUpperCase();
}

function incrementNumber() {
  number.value = number.value + 1;
}

let wizard = ref({
  id: 1001,
  name: 'Gandalf',
  house: 'Grey',
  age: 2019,
  wand: {
    wood: 'Olive',
    core: 'Dragon heartstring',
    length: 36
  }
})

function changeNameToUpperCase() {
  wizard.value.name = wizard.value.name.toUpperCase();
}

function changeWandCore() {
  wizard.value.wand.core = 'Unicorn hair';
}

function changeWizard() {
  wizard.value = {
    id: 1002,
    name: 'Dumbledore',
    house: 'Gryffindor',
    age: 115,
    wand: {
      wood: 'Elder',
      core: 'Thestral tail hair',
      length: 15
    }
  }
};
let wizards = ref([
    {
      id: 1001,
      name: 'Gandalf',
      house: 'Grey',
      age: 2019,
      wand: {
        wood: 'Olive',
        core: 'Dragon heartstring',
        length: 36
      }
    },
    {
      id: 1002,
      name: 'Dumbledore',
      house: 'Gryffindor',
      age: 115,
      wand: {
        wood: 'Elder',
        core: 'Thestral tail hair',
        length: 15
      }
    },
    {
      id: 1003,
      name: 'Merlin',
      house: 'Camelot',
      age: 1500,
      wand: {
        wood: 'Yew',
        core: 'Phoenix feather',
        length: 18
      }
    }
  ]);

</script>

<style scoped>
.card {
  background-color: purple;
  color: white;
  padding: 20px 10px;
  margin-bottom: 10px;
}
</style>