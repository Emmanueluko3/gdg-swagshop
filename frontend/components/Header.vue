<template>
  <nav
    class="bg-customWhite fixed w-full flex justify-between items-center py-6 px-20 drop-shadow-md"
  >
    <a class="w-72" href="/">
      <img :src="navLogo" class="w-full h-full" alt="Logo" />
    </a>

    <div class="flex items-center" :class="{ 'is-active': isActive }">
      <a
        v-for="(item, index) in navLinks"
        :key="index"
        class="mx-6 hover:opacity-60"
        :href="item.href"
        ><img :src="item.icon" alt="" class="w-6 h-6"
      /></a>
    </div>
  </nav>
</template>

<script>
import GDGLogo from "../assets/images/gdgLogo.svg";
import SeachIcon from "../assets/icons/search.svg";
import CartIcon from "../assets/icons/cart.svg";
import UserIcon from "../assets/icons/user.svg";

export default {
  name: "Header",
  data() {
    return {
      isActive: false,
      navLogo: GDGLogo,
      navLinks: [
        { icon: SeachIcon, href: "/search" },
        { icon: CartIcon, href: "/cart" },
        { icon: UserIcon, href: "/profile" },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.isActive = !this.isActive;
    },
  },
};
</script>

<!-- const route = useRoute();
const currentRoute = route.path; -->
