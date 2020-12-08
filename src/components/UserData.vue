<template>
  <section class="adduser">
    <form @submit.prevent="submitData">
      <div>
        <input type="text" placeholder="Your name" v-model="enteredName" />
      </div>
      <div>
        <input type="number" placeholder="Your age" v-model="enteredAge" />
      </div>
      <div>
        <button>Add User</button>
      </div>
    </form>
  </section>
</template>

<script>
export default {
  emits: ["new-user"],
  data() {
    return {
      enteredName: "",
      enteredAge: "",
    };
  },
  methods: {
    submitData() {
      this.$emit("new-user", this.enteredName, this.enteredAge);
    },
  },
};
</script>
