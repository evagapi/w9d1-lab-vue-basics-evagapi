<template>
  <div class="p-4 bg-green-100 leading-loose">
    <h2 class="text-lg font-bold mb-2">This is my form:</h2>
    <form action="post" class="mb-8">
      <fieldset>
        <Input
          type="text"
          id="name"
          label="Name: "
          placeholder="Name"
          v-model="name"
        />
      </fieldset>
      <fieldset>
        <Input
          type="email"
          id="email"
          placeholder="E-mail"
          label="Email: "
          v-model="email"
        />
      </fieldset>
      <fieldset class="mb-4">
        <label for="pet-select" class="mr-2 w-20 inline-block">Pet: </label>
        <select
          name="pet"
          id="pet-select"
          class="p-4 w-80 rounded"
          v-model="pet"
        >
          <option value="❓">--Please choose an option--</option>
          <option value="🐶">Dog</option>
          <option value="🐱">Cat</option>
          <option value="🐹">Hamster</option>
          <option value="🦜">Parrot</option>
          <option value="🐍">Snake</option>
          <option value="🐠">Fish</option>
        </select>
      </fieldset>
      <fieldset>
        <legend>Which cheese do you like?:</legend>
        <Checkbox id="stilton" label="Stilton" v-model="stilton" />
        <Checkbox id="pecorino" label="Pecorino" v-model="pecorino" />
        <Checkbox id="parmigiano" label="Parmigiano" v-model="parmigiano" />
      </fieldset>
      <fieldset class="mb-4">
        <label for="enter-a-number" class="mr-2 w-30 inline-block"
          >Enter a number:
        </label>
        <input
          type="number"
          id="enter-a-number"
          placeholder="Number"
          v-model="number"
          class="p-4 w-80 rounded"
        />
      </fieldset>
    </form>
    <div>
      <h2 class="text-lg font-bold mb-2">Two-way Data Binding:</h2>
      <div class="p-4 bg-slate-100">
        <p>Your name is: {{ name }}</p>
        <p>Your e-mail is: {{ email }}</p>
        <p>Your pet is: {{ pet }}</p>
        <p>You like Stilton: {{ stilton }}</p>
        <p>You like Pecorino: {{ pecorino }}</p>
        <p>You like Parmigiano: {{ parmigiano }}</p>
        <p>Your number is: <EvenOrOdd :number="number" /></p>
      </div>
    </div>
  </div>
</template>
<script>
import Checkbox from "./Checkbox.vue";
import Input from "./Input.vue";
import EvenOrOdd from "./EvenOrOdd.vue";

export default {
  data() {
    return {
      name: null,
      email: null,
      pet: "❓",
      stilton: false,
      pecorino: false,
      parmigiano: false,
      number: 0,
    };
  },
  components: { Checkbox, Input, EvenOrOdd },
};
</script>
