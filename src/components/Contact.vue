<template>
  <div class="neumorphic-form">
    <div class="form-group">
      <label for="name">Name:</label>
      <input
        v-model="formData.name"
        type="text"
        id="name"
        class="input-field"
        placeholder="Enter your name"
      />
    </div>

    <div class="form-group">
      <label for="email">Email:</label>
      <input
        v-model="formData.email"
        type="email"
        id="email"
        class="input-field"
        placeholder="Enter your email"
      />
    </div>

    <div class="form-group">
      <label for="message">Message:</label>
      <textarea
        v-model="formData.message"
        id="message"
        class="input-field"
        rows="4"
        placeholder="Enter your message"
      ></textarea>
    </div>

    <button @click="submitForm" class="submit-button">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: '',
      },
    };
  },
  methods: {
    submitForm() {
      // Handle form submission logic here
      console.log('Form submitted:', this.formData);
    },
  },
};
</script>

<style scoped>
.neumorphic-form {
  background-color: #f0f0f0;
  border-radius: 20px;
  padding: 20px;
  width: 300px;
  box-shadow: 10px 10px 20px #cbcbcb, -10px -10px 20px #ffffff;
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 15px;
}

.input-field {
  padding: 10px;
  border: none;
  border-radius: 10px;
  box-shadow: inset 6px 6px 10px #cbcbcb, inset -6px -6px 10px #ffffff;
}

.submit-button {
  background-color: #3498db;
  color: #fff;
  padding: 10px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  box-shadow: 6px 6px 10px #3498db, -6px -6px 10px #80bfff;
}
</style>

