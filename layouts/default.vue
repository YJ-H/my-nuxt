<template>
  <el-container class="containerMain">
    <el-header>
      <el-menu :default-active="activeIndex" class="el-menu-demo menu-top" mode="horizontal">
        <el-menu-item index="1"><a href="https://cn.vuejs.org/" class="topLink" target="_blank">Vue</a></el-menu-item>
        <el-menu-item index="2"><a href="https://nuxtjs.org/guide" class="topLink" target="_blank">Nuxt</a></el-menu-item>
      </el-menu>
    </el-header>
    <el-container class="containerMain">
      <el-aside width="200px">
        <ul>
          <li v-for="(menu,index) in menus" :key="index" class="nav-item">
            <a :href="menu.href" :class="[$route.path === menu.href ? 'active' : '']">{{ menu.name }}</a>
          </li>
        </ul>
      </el-aside>
      <el-main>
        <nuxt/>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
import menus from "~/assets/menu.js";
export default {
  asyncData ({params}) {
    return {
      activeIndex: '',
    }
  },
  data () {
    return {
      a: 1,
      activeIndex: '',
      menus: menus
    }
  },
   mounted () {
    console.log(this.$route)
  },
}
</script>


<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
#__nuxt,#__layout {
  height: 100%;
}
</style>

<style lang="less">
  html {
    height: 100%;
    body {
      height: 100%;
    }
    .line-margin {
      margin-bottom: 10px;
    }
    header.el-header {
      padding-left: 0px;
    }
    .containerMain {
      height: 100%;
    }
    aside.el-aside {
      margin-top: 20px; 
      height: 100%;
    }
    .nav-item {
      font-size: 12px;
      color: #999;
      line-height: 26px;
      margin-top: 15px;
      display: list-item;
      text-align: -webkit-match-parent;
      font-size: 16px;
      list-style: none;
      a {
        color:  #999;
        text-decoration: none;
      }
      a.active {
        color: #409eff;
      }
    }
    .menu-top {
      padding-left: 220px;
      li.el-menu-item {
        
        color: #000;
        font-family: -apple-system,SF UI Text,Arial,PingFang SC,Hiragino Sans GB,Microsoft YaHei,WenQuanYi Micro Hei,sans-serif;
        .topLink {
          display: block;
        }
      }
    }
    .page {
      margin-left: 10px;
    }
  }
</style>

