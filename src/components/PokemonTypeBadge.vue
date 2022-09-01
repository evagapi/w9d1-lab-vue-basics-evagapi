<template>
  <li :class="`px-2 py-1 ${type} border-2 rounded font-bold`">
    {{ type }}
  </li>
</template>

<script>
export default {
  props: {
    type: String,
  },
};
</script>

<style scoped>
.normal {
  background-color: #a8a878;
  border-color: #705848;
}
.grass {
  background-color: #78c850;
  border-color: #588040;
}
.fire {
  background-color: #f08030;
  border-color: #c03028;
}

.electric {
  background-color: #f8d030;
  border-color: #b8a038;
}
.water {
  background-color: #6890f0;
  border-color: #3a5085;
}

.ice {
  background-color: #98d8d8;
  border-color: #9090a0;
}
.fighting {
  background-color: #c03028;
  border-color: #484038;
}
.poison {
  background-color: #a040a0;
  border-color: #483850;
}
.ground {
  background-color: #e0c068;
  border-color: #886830;
}
.flying {
  background-color: #a890f0;
  border-color: #705898;
}
.psychic {
  background-color: #f85888;
  border-color: #9e2e4f;
}
.bug {
  background-color: #a8b820;
  border-color: #6a721e;
}
.rock {
  background-color: #b8a038;
  border-color: #886830;
}

.ghost {
  background-color: #705898;
  border-color: #483850;
}
.dark {
  background-color: #705848;
  border-color: #484038;
}
.dragon {
  background-color: #7038f8;
  border-color: #483890;
}

.steel {
  background-color: #b8b8d0;
  border-color: #807870;
}

.fairy {
  background-color: #f0b6bc;
  border-color: #c2656f;
}
</style>
