
<template>
  <header class="Header">
    <div>
      <img src="~/assets/img/logo.png" alt="物研iot" />
    </div>
    <nav>
      <ul>
        <li v-for="(route, index) in routes" key="index">
          <NuxtLink :to="route.path">{{ route.title }}</NuxtLink>
        </li>
        
      </ul>
    </nav>
  </header>
</template>

<script setup>
const routes = [
  {
    path: '/',
    title: '首页'
  },
  {
    path: '/about',
    title: '关于'
  },
  {
    path: '/productAndService/hardware',
    title: '产品与服务',
    children: [
      {
        path: '/productAndService/hardware',
        title: '智能硬件'
      },
      {
        path: '/productAndService/iot',
        title: '物联网平台'
      },
      {
        path: '/productAndService/iotAbility',
        title: '物联网平台-能力'
      },
    ]
  }
]
</script>

<style lang="scss" scoped>
.Header {
  display: flex;
  height: 60px;
  border-bottom: 1px solid #cccccc;
  line-height: 60px;

  img {
    width: 80px;
  }

  ul {
    display: flex;
    li {
      margin-right: 10px;
    }
  }
}

</style>