<template>
  <nav
    class="absolute bottom-0 flex items-center justify-between w-full text-white bg-gray-800 navbar"
  >
    <div
      class="z-10 flex items-center justify-between w-full py-4 xl:justify-start brand-wrapper"
    >
      <img
        src="../assets/logo-xs.png"
        alt="Logo SMAN 1 Rawamerta"
        class="w-10 ml-4 brand-logo xl:w-12"
      />
      <a href="/" class="text-lg font-semibold xl:ml-4 brand xl:text-xl"
        >SMA Negeri 1 Rawamerta</a
      >
      <button class="mr-6 toggle-menu-m" type="button" @click="toggleMenu">
        <fa icon="fa-solid fa-bars" size="lg"></fa>
      </button>
    </div>
    <ul
      class="fixed top-0 w-1/2 h-full bg-gray-800 nav-menu"
      :class="toggleMenuMobile"
    >
      <li class="nav-list">
        <a href="/" class="nav-link">Home</a>
      </li>
      <li class="nav-list">
        <a href="/services" class="nav-link">Services</a>
      </li>
      <li class="nav-list">
        <a href="/about" class="nav-link">About</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      toggleMenuMobile: "-left-full",
    };
  },
  methods: {
    toggleMenu() {
      if (this.toggleMenuMobile == "left-0") {
        this.toggleMenuMobile = "-left-full";
      } else {
        this.toggleMenuMobile = "left-0";
      }
    },
  },
};
</script>
