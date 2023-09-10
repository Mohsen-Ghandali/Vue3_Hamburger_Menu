<template>
  <main>
    <h1>{{ title }}</h1>
    <div v-if="openMenu">
      <Modal
        :menuItems="menuItems"
        :textMenu="textMenu"
        @close-menu="changeMenu"
      />
    </div>
    <button @click="changeMenu">
      <div></div>
      <div></div>
      <div></div>
    </button>
  </main>
</template>

<script lang="ts">
import Modal from "./components/HamburgerMenu.vue";

export default {
  name: "App",
  components: { Modal },

  data() {
    return {
      title: "Hallo-Welt",

      menuItems: [
        {
          item: "Home",
          link: "#",
        },
        {
          item: "Products",
          link: "#",
        },
        {
          item: "About us",
          link: "#",
        },
        {
          item: "Contact us",
          link: "#",
        },
      ],

      textMenu: "Hamburger Menu",
      openMenu: false,
    };
  },

  methods: {
    changeMenu(this: any): void {
      this.openMenu = !this.openMenu;
    },
  },
};
</script>

<style scoped lang="scss">
main {
  margin: 0 auto;
  text-align: center;
  h1 {
    font: bold 32px arial;
    text-align: center;
    margin: 68px 0;
  }
  button {
    position: absolute;
    top: 16px;
    right: 16px;
    padding: 6px 16px;
    border-radius: 4px;
    margin-left: 4px;
    border: none;
    cursor: pointer;
    background-color: transparent;
    color: #ebebeb;

    div {
      width: 32px;
      height: 4px;
      margin-bottom: 4px;
      background-color: blueviolet;
      border-radius: 4px;
      z-index: 100;
    }
  }
}
</style>
