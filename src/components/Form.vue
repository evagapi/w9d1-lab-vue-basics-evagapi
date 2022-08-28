<template>
  <div>
    <p>This is my form:</p>
    <form action="post">
      <fieldset>
        <label for="name">Name: </label>
        <input
          type="text"
          v-model="name"
          name="name"
          id="name"
          placeholder="Name"
        />
      </fieldset>
      <fieldset>
        <label for="email"> Email: </label>
        <input
          type="email"
          v-model="email"
          name="email"
          id="email"
          placeholder="E-mail"
        />
      </fieldset>
      <fieldset>
        <label for="pet-select">Pet: </label>
        <select name="pet" id="pet-select" v-model="pet">
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
        <legend>Choose as many cheese as you like:</legend>
        <div>
          <input
            type="checkbox"
            id="stilton"
            name="stilton"
            v-model="stilton"
          />
          <label for="stilton">Stilton</label>
        </div>
        <div>
          <input
            type="checkbox"
            id="pecorino"
            name="pecorino"
            v-model="pecorino"
          />
          <label for="pecorino">Pecorino</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="parmigiano"
            id="parmigiano"
            v-model="parmigiano"
          />
          <label for="parmigiano">Parmigiano</label>
        </div>
      </fieldset>
    </form>
    <div>
      <p>Two-way Data Binding:</p>
      <p>Your name is: {{ name }}</p>
      <p>Your e-mail is: {{ email }}</p>
      <p>Your pet is: {{ pet }}</p>
      <p>You like Parmigiano: {{ stilton }}</p>
      <p>You like Parmigiano: {{ pecorino }}</p>
      <p>You like Parmigiano: {{ parmigiano }}</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: null,
      email: null,
      pet: "❓",
      stilton: false,
      pecorino: false,
      parmigiano: false,
    };
  },
};
</script>
