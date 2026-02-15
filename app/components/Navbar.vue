<template>
  <nav
    style="
      background: #1a1a1a;
      padding: 1rem;
      position: sticky;
      top: 0;
      z-index: 100;
    "
  >
    <div
      style="
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
      "
    >
      <!-- Logo -->
      <NuxtLink
        to="/"
        style="
          color: white;
          text-decoration: none;
          font-size: 1.5rem;
          font-weight: bold;
        "
      >
        MyPortfolio
      </NuxtLink>

      <!-- Navigation Links -->
      <div style="display: flex; gap: 2rem">
        <NuxtLink to="/" style="color: white; text-decoration: none"
          >Home</NuxtLink
        >
        <NuxtLink to="/projects" style="color: white; text-decoration: none"
          >Projects</NuxtLink
        >
        <NuxtLink to="/contact" style="color: white; text-decoration: none"
          >Contact</NuxtLink
        >
      </div>
    </div>
  </nav>
</template>
