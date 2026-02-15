<template>
  <div>
    <h1 style="font-size: 2.5rem; margin-bottom: 1rem">My Projects</h1>
    <p style="color: #666; margin-bottom: 3rem; font-size: 1.1rem">
      Here are some of the projects I've worked on. Each one taught me something
      new.
    </p>

    <div
      style="
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
        gap: 2rem;
      "
    >
      <ProjectCard
        v-for="project in projects"
        :key="project.id"
        :project="project"
      />
    </div>
  </div>
</template>

<script setup>
import { projects } from "~/data/projects";
</script>
