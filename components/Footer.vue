<template>
  <footer class="footer">
    <img src="~/assets/img/logo.png" alt="">
    <span>
      <NuxtLink to="https://github.com/xxyu98/nuxt-study" target="_blank">
        nuxt-study
      </NuxtLink>
    </span>
  </footer>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.footer {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  height: 60px;
  justify-content: center;
  align-items: center;
  background-color: #272727;

  img {
    width: 24px;
    height: 24px;
    margin-right: 20px;
  }

  span {
    color: rgba(255, 255, 255, .86);
    cursor: pointer;
  }

  span:hover {
    color: #ffffff;
  }
}
</style>