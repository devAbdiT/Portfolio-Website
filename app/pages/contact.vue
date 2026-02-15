<template>
  <div style="max-width: 600px; margin: 0 auto">
    <h1 style="font-size: 2.5rem; margin-bottom: 1rem; text-align: center">
      Get In Touch
    </h1>
    <p style="color: #666; margin-bottom: 3rem; text-align: center">
      Have a project in mind? Let's work together!
    </p>

    <form
      @submit.prevent="handleSubmit"
      style="background: #f8f9fa; padding: 2rem; border-radius: 12px"
    >
      <!-- Name -->
      <div style="margin-bottom: 1.5rem">
        <label style="display: block; margin-bottom: 0.5rem; font-weight: 500"
          >Name</label
        >
        <input
          v-model="form.name"
          type="text"
          required
          style="
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
          "
          placeholder="Your name"
        />
      </div>

      <!-- Email -->
      <div style="margin-bottom: 1.5rem">
        <label style="display: block; margin-bottom: 0.5rem; font-weight: 500"
          >Email</label
        >
        <input
          v-model="form.email"
          type="email"
          required
          style="
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
          "
          placeholder="your@email.com"
        />
      </div>

      <!-- Message -->
      <div style="margin-bottom: 1.5rem">
        <label style="display: block; margin-bottom: 0.5rem; font-weight: 500"
          >Message</label
        >
        <textarea
          v-model="form.message"
          rows="5"
          required
          style="
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            resize: vertical;
          "
          placeholder="Tell me about your project..."
        ></textarea>
      </div>

      <!-- Submit -->
      <button
        type="submit"
        :disabled="isSubmitting"
        style="
          width: 100%;
          background: #007bff;
          color: white;
          border: none;
          padding: 1rem;
          font-size: 1.1rem;
          border-radius: 8px;
          cursor: pointer;
          font-weight: 500;
          transition: background 0.2s;
        "
        :style="{ background: isSubmitting ? '#6c757d' : '#007bff' }"
      >
        {{ isSubmitting ? "Sending..." : "Send Message" }}
      </button>

      <!-- Success Message -->
      <div
        v-if="isSubmitted"
        style="
          margin-top: 1rem;
          padding: 1rem;
          background: #d4edda;
          color: #155724;
          border-radius: 8px;
          text-align: center;
        "
      >
        ✓ Message sent! I'll get back to you soon.
      </div>
    </form>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue";

const form = reactive({
  name: "",
  email: "",
  message: "",
});

const isSubmitting = ref(false);
const isSubmitted = ref(false);

function handleSubmit() {
  isSubmitting.value = true;

  // Simulate sending
  setTimeout(() => {
    console.log("Form submitted:", form);
    isSubmitting.value = false;
    isSubmitted.value = true;

    // Reset form
    form.name = "";
    form.email = "";
    form.message = "";

    // Hide success message after 3 seconds
    setTimeout(() => {
      isSubmitted.value = false;
    }, 3000);
  }, 1000);
}
</script>
