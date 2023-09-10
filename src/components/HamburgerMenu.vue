<template lang="">
  <div class="bgDrop" @click.self="closeMenu">
    <div class="menu">
      <span @click.self="closeMenu">X</span>
      <h3>{{ textMenu }}</h3>
      <hr />
      <ul>
        <li v-for="menuItem in menuItems">
          <a :href="menuItem.link">{{ menuItem.item }}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: ["menuItems", "textMenu"],
  methods: {
    closeMenu(this: any): void {
      this.$emit("close-menu");
    },
  },
};
</script>

<style scoped lang="scss">
@keyframes hamburgerMenu {
  from {right:  -100%;}
  to {right: 0;}
}
.bgDrop {
  position: fixed;
  top: 0;
  left: 0;
  background-color: rgb(0, 0, 0, 0.2);
  height: 100dvh;
  width: 100%;
  z-index: 150;
  .menu {
    position: fixed;
    top: 0;
    right: 0;
    width: 40%;
    height: 100dvh;
    padding: 20px;
    background-color:rgb(236, 236, 236);
    font: bold 24px arial;
    color: #272727;
    box-shadow: 0px 2px 16px rgb(0, 0, 0, 0.5);
    animation: hamburgerMenu 500ms ; 
    span {
      position: absolute;
      left: 12px;
      top: 12px;
      color: #272727;
      width: 24px;
      height: 24px;
      font: 100 24px arial;
      cursor: pointer;
    }
    h3{
      margin: 32px 0 24px 0;
    }
    hr{
      width: 50%;
      margin: 0 auto 48px auto;
    }
  }
  ul{
    list-style: none;
    li{
      margin: 24px 0;
      a{
        text-decoration: none;
        color: #4b4b4b;
      }
    }
  }
}
</style>
