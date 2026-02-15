<template>
  <div
    style="
      border: 1px solid #e0e0e0;
      border-radius: 12px;
      overflow: hidden;
      transition:
        transform 0.2s,
        box-shadow 0.2s;
      background: white;
      height: 100%;
      display: flex;
      flex-direction: column;
    "
    @mouseover="hover = true"
    @mouseleave="hover = false"
  >
    <!-- Image -->
    <img
      :src="project.image"
      :alt="project.title"
      style="width: 100%; height: 200px; object-fit: cover"
    />

    <!-- Content -->
    <div
      style="padding: 1.5rem; flex: 1; display: flex; flex-direction: column"
    >
      <h3 style="margin: 0 0 0.5rem 0; font-size: 1.25rem">
        {{ project.title }}
      </h3>
      <p style="color: #666; margin-bottom: 1rem; line-height: 1.6; flex: 1">
        {{ project.description }}
      </p>

      <!-- Technologies -->
      <div
        style="
          display: flex;
          gap: 0.5rem;
          flex-wrap: wrap;
          margin-bottom: 1.5rem;
        "
      >
        <span
          v-for="tech in project.technologies.slice(0, 3)"
          :key="tech"
          style="
            background: #f0f0f0;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.8rem;
            color: #555;
          "
        >
          {{ tech }}
        </span>
        <span
          v-if="project.technologies.length > 3"
          style="
            background: #f0f0f0;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.8rem;
            color: #555;
          "
          >+{{ project.technologies.length - 3 }}</span
        >
      </div>

      <!-- Buttons -->
      <div style="display: flex; gap: 0.75rem">
        <a
          :href="project.liveUrl"
          target="_blank"
          style="
            background: #007bff;
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 6px;
            text-decoration: none;
            font-size: 0.9rem;
            transition: background 0.2s;
            flex: 1;
            text-align: center;
          "
          @mouseover="$event.target.style.background = '#0056b3'"
          @mouseleave="$event.target.style.background = '#007bff'"
        >
          Live Demo
        </a>

        <NuxtLink
          :to="`/projects/${project.id}`"
          style="
            background: #6c757d;
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 6px;
            text-decoration: none;
            font-size: 0.9rem;
            transition: background 0.2s;
            flex: 1;
            text-align: center;
          "
          @mouseover="$event.target.style.background = '#545b62'"
          @mouseleave="$event.target.style.background = '#6c757d'"
        >
          Details
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

defineProps({
  project: {
    type: Object,
    required: true,
  },
});

const hover = ref(false);
</script>
