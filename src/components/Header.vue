<template>
  <nav
    class="absolute bottom-0 flex items-center justify-between w-full text-white bg-gray-800 navbar xl:relative"
  >
    <div
      class="z-10 flex items-center justify-between w-full py-4 xl:justify-start brand-wrapper xl:z-auto"
    >
      <img
        src="../assets/logo-xs.png"
        alt="Logo SMAN 1 Rawamerta"
        class="w-10 ml-4 brand-logo xl:w-12"
      />
      <a href="/" class="text-lg font-semibold xl:ml-4 brand xl:text-xl"
        >SMA Negeri 1 Rawamerta</a
      >
      <button
        class="mr-6 toggle-menu-m xl:hidden"
        type="button"
        @click="toggleMenu"
      >
        <fa icon="fa-solid fa-bars" size="lg"></fa>
      </button>
    </div>
    <ul
      class="fixed top-0 w-1/2 h-full bg-gray-800 xl:h-auto nav-menu xl:relative"
      :class="toggleMenuMobile"
    >
      <li class="nav-list">
        <a href="/" class="nav-link">Home</a>
      </li>
      <li class="nav-list dropdown">
        <a href="/services" class="nav-link" @click="toggleDropdown($event)"
          >Services
          <fa icon="fa-solid fa-caret-down" class="ml-1" size="sm"></fa>
        </a>
        <ul class="hidden xl:block xl:invisible xl:opacity-0 dropdown-menu">
          <li class="drop-list">
            <a href="/contact" class="drop-link">Contact Us</a>
          </li>
          <li class="drop-list">
            <a href="/contact" class="drop-link">Contact Us</a>
          </li>
          <li class="drop-list">
            <a href="/contact" class="drop-link">Contact Us</a>
          </li>
        </ul>
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
      toggleMenuMobile: window.innerWidth > 1279 ? "" : "-left-full",
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
    toggleDropdown(e) {
      e.preventDefault();
      if (window.innerWidth >= 1280) {
        this.dropdownToggleDesktop(e);
      } else {
        this.dropdownToggleMobile(e);
      }
    },
    dropdownToggleDesktop(e) {
      const dropdown = e.target.parentNode.lastChild.classList;
      if (dropdown.contains("xl:invisible")) {
        dropdown.remove("xl:invisible");
        dropdown.remove("xl:opacity-0");
        dropdown.add("xl:visible");
        dropdown.add("xl:opacity-100");
      } else {
        dropdown.remove("xl:visible");
        dropdown.remove("xl:opacity-100");
        dropdown.add("xl:invisible");
        dropdown.add("xl:opacity-0");
      }
    },
    dropdownToggleMobile(e) {
      const dropdown = e.target.parentNode.lastChild.classList;
      if (dropdown.contains("hidden")) {
        dropdown.remove("hidden");
      } else {
        dropdown.add("hidden");
      }
    },
  },
};
</script>
