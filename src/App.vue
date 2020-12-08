<template>
  <user-data @new-user="newUser"></user-data>
  <active-user :name="user.name" :age="user.age"></active-user>
</template>

<script>
export default {
  data() {
    return {
      // Default Values  
      user: {
        name: "David",
        age: 35,
      },
    };
  },
  methods: {
    newUser(name, age) {
        this.user = {
            name: name,
            age: +age  //+age converts the string to a number, this is required so there are no warnings from Active User props
        }
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

section {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  border: 1px solid #ccc;
  padding: 1rem;
}

form > * {
  padding: 5px;
}

.adduser {
  text-align: center;
}
</style>
