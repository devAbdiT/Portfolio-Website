<template>
  <div>
    <NuxtLink
      to="/projects"
      style="
        display: inline-block;
        margin-bottom: 2rem;
        color: #666;
        text-decoration: none;
      "
    >
      ← Back to Projects
    </NuxtLink>

    <div
      v-if="project"
      style="
        background: white;
        border-radius: 12px;
        overflow: hidden;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      "
    >
      <!-- Image -->
      <img
        :src="project.image"
        :alt="project.title"
        style="width: 100%; max-height: 400px; object-fit: cover"
      />

      <!-- Content -->
      <div style="padding: 2rem">
        <h1 style="font-size: 2.5rem; margin-bottom: 1rem">
          {{ project.title }}
        </h1>

        <div style="margin-bottom: 2rem">
          <h2 style="font-size: 1.5rem; margin-bottom: 1rem">Overview</h2>
          <p style="line-height: 1.8; color: #444">
            {{ project.longDescription }}
          </p>
        </div>

        <!-- Technologies -->
        <div style="margin-bottom: 2rem">
          <h2 style="font-size: 1.5rem; margin-bottom: 1rem">
            Technologies Used
          </h2>
          <div style="display: flex; gap: 0.75rem; flex-wrap: wrap">
            <span
              v-for="tech in project.technologies"
              :key="tech"
              style="
                background: #e9ecef;
                padding: 0.5rem 1rem;
                border-radius: 25px;
                font-size: 1rem;
              "
            >
              {{ tech }}
            </span>
          </div>
        </div>

        <!-- Links -->
        <div style="display: flex; gap: 1rem">
          <a
            :href="project.liveUrl"
            target="_blank"
            style="
              background: #007bff;
              color: white;
              padding: 1rem 2rem;
              border-radius: 8px;
              text-decoration: none;
              display: inline-block;
            "
          >
            View Live Project
          </a>

          <a
            :href="project.githubUrl"
            target="_blank"
            style="
              background: #333;
              color: white;
              padding: 1rem 2rem;
              border-radius: 8px;
              text-decoration: none;
              display: inline-block;
            "
          >
            View on GitHub
          </a>
        </div>
      </div>
    </div>

    <div v-else style="text-align: center; padding: 3rem">
      <p style="font-size: 1.2rem">Project not found!</p>
      <NuxtLink to="/projects" style="color: #007bff"
        >Browse all projects</NuxtLink
      >
    </div>
  </div>
</template>

<script setup>
import { projects } from "~/data/projects";

const route = useRoute();
const projectId = parseInt(route.params.id);
const project = projects.find((p) => p.id === projectId);
</script>
