<template>
  <div style="display: flex; flex-direction: column; min-height: 100vh">
    <Navbar />

    <main
      style="
        flex: 1;
        max-width: 1200px;
        margin: 2rem auto;
        padding: 0 1rem;
        width: 100%;
      "
    >
      <slot />
    </main>

    <Footer />
  </div>
</template>

<script setup></script>
