<template>
  <nav
    class="flex items-center justify-between w-full text-white bg-gray-800 navbar"
  >
    <div
      class="flex items-center justify-between w-full py-4 xl:justify-start brand-wrapper"
    >
      <img
        src="../assets/logo-xs.png"
        alt="Logo SMAN 1 Rawamerta"
        class="w-10 ml-4 brand-logo xl:w-12"
      />
      <a href="/" class="text-lg font-semibold xl:ml-4 brand xl:text-xl"
        >SMA Negeri 1 Rawamerta</a
      >
      <button class="mr-6 toggle-menu-m" type="button">
        <fa icon="fa-solid fa-bars" size="lg"></fa>
      </button>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>
