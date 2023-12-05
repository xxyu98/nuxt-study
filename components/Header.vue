<template>
  <header class="fixHeader">
    <div class="container">
      <div class="left-bar">
        <NuxtLink to="/">
          <img src="~/assets/img/logo.png" alt="官网logo" />
        </NuxtLink>
      </div>
      <nav class="navs">
        <ul>
          <li v-for="route in routes" :key="route.path">
            <NuxtLink :to="route.path">{{ route.title }}</NuxtLink>
            <div class="menu" v-if="route.children">
              <div class="menu-item" v-for="menu in route.children" :key="menu.path">
                <NuxtLink :to="menu.path">{{ menu.title }}</NuxtLink>
              </div>
            </div>
          </li>
        </ul>
      </nav>
      <div class="right-bar">
        <div class="link">
          <NuxtLink to="https://github.com/xxyu98/nuxt-study" target="_blank">
            项目链接
          </NuxtLink>
        </div>
      </div>
    </div>
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
    path: '/multi/iot',
    title: '产品与服务',
    children: [
      {
        path: '/multi/iot',
        title: '物联网平台'
      },
      {
        path: '/multi/iotAbility',
        title: '平台能力'
      },
    ]
  }
]
</script>

<style lang="scss" scoped>
.fixHeader {
  position: sticky;
  top: 0;
  height: var(--nav-height);
  border-bottom: 1px solid rgba(60, 60, 60, .12);
  line-height: 60px;
  color: #213547;
  font-size: 14px;
  background-color: rgba(255, 255, 255, .8);
  backdrop-filter: saturate(180%) blur(20px);
  z-index: 10;

  .container {
    display: flex;

    .left-bar {
      width: 200px;
      display: flex;
      align-items: center;

      img {
        height: 28px;
      }
    }

    .navs {
      flex: 1;
      display: flex;
      justify-content: center;

      ul {
        display: flex;

        li {
          position: relative;
          padding: 0 12px;

          .menu {
            position: absolute;
            top: 46px;
            padding: 12px 0;
            box-shadow: 0 12px 32px rgba(0, 0, 0, .1), 0 2px 6px rgba(0, 0, 0, .08);
            background-color: #ffffff;
            border-radius: 8px;
            opacity: 0;
            visibility: hidden;
            transition: opacity .25s, visibility .25s, transform .25s;

            .menu-item {
              padding: 0 18px;
              line-height: 28px;
              white-space: nowrap;
            }
          }
        }

        a {
          transition: color .25s;
        }

        a:hover {
          color: #42b883;
        }

        li:hover .menu {
          opacity: 1;
          visibility: visible;
        }
      }
    }

    .right-bar {
      width: 200px;
      display: flex;
      align-items: center;
      justify-content: flex-end;

      .link {
        cursor: pointer;
      }
    }
  }
}
</style>