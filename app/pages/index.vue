<script setup>
import { projects } from "../data/projects";
const skills = [
  "React",
  "Next",
  "JavaScript",
  "HTML5",
  "CSS3",
  "Git",
  "REST APIs",
  "Tailwind",
  "Typscript",
];
const featuredProjects = projects.slice(0, 2); // Show first 2 projects
</script>
<template>
  <div>
    <!-- Hero Section -->
    <section
      style="
        background: linear-gradient(135deg, #4b5563 0%, #1f2937 100%);
        color: white;
        padding: 4rem 2rem;
        text-align: center;
      "
    >
      <div style="max-width: 700px; margin: 0 auto">
        <h1 style="font-size: 3rem; margin-bottom: 1rem; font-weight: 600">
          Hi, I'm Abdi Tadesse
        </h1>

        <p style="font-size: 1.3rem; margin-bottom: 1.5rem; opacity: 0.95">
          Frontend Web Developer
        </p>

        <p
          style="
            font-size: 1.1rem;
            margin-bottom: 2.5rem;
            opacity: 0.9;
            line-height: 1.6;
          "
        >
          I build responsive websites and web applications with modern
          technologies like React and Next
        </p>

        <NuxtLink to="/projects">
          <button
            style="
              background: white;
              color: #764ba2;
              border: none;
              padding: 0.8rem 2rem;
              font-size: 1rem;
              border-radius: 5px;
              cursor: pointer;
              font-weight: 600;
              border: 2px solid transparent;
              transition: all 0.2s;
            "
          >
            View My Work
          </button>
        </NuxtLink>
      </div>
    </section>

    <!-- About Section -->
    <section style="margin-bottom: 4rem">
      <h2 style="font-size: 2rem; margin-bottom: 2rem; text-align: center">
        About Me
      </h2>
      <div
        style="display: flex; gap: 3rem; align-items: center; flex-wrap: wrap"
      >
        <div style="flex: 1; min-width: 300px">
          <p style="line-height: 1.8; color: #444; margin-bottom: 1rem">
            I'm a junior frontend developer passionate about building clean and
            responsive web interfaces. I enjoy learning new technologies and
            turning ideas into reality through code.
          </p>
          <p style="line-height: 1.8; color: #444">
            When I'm not coding, you can find me exploring new technologies,
            contributing to open source, or enjoying a good cup of coffee.
          </p>
        </div>
        <div style="flex: 1; min-width: 300px">
          <div style="background: #f8f9fa; padding: 2rem; border-radius: 12px">
            <h3 style="margin-bottom: 1rem">Skills</h3>
            <div style="display: flex; flex-wrap: wrap; gap: 0.5rem">
              <span
                v-for="skill in skills"
                :key="skill"
                style="
                  background: #e9ecef;
                  padding: 0.5rem 1rem;
                  border-radius: 25px;
                  font-size: 0.9rem;
                "
                >{{ skill }}</span
              >
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Featured Projects -->
    <section>
      <h2 style="font-size: 2rem; margin-bottom: 2rem; text-align: center">
        Featured Projects
      </h2>
      <div
        style="
          display: grid;
          grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
          gap: 2rem;
        "
      >
        <ProjectCard
          v-for="project in featuredProjects"
          :key="project.id"
          :project="project"
        />
      </div>
      <div style="text-align: center; margin-top: 2rem">
        <NuxtLink to="/projects">
          <button
            style="
              background: transparent;
              border: 2px solid #007bff;
              color: #007bff;
              padding: 0.75rem 2rem;
              border-radius: 25px;
              cursor: pointer;
              font-size: 1rem;
              transition: all 0.2s;
            "
            @mouseover="
              $event.target.style.background = '#007bff';
              $event.target.style.color = 'white';
            "
            @mouseleave="
              $event.target.style.background = 'transparent';
              $event.target.style.color = '#007bff';
            "
          >
            See All Projects
          </button>
        </NuxtLink>
      </div>
    </section>
  </div>
</template>
