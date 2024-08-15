<template>
  <div class="home">
    <el-container class="full-height">
      <el-aside width="250px" class="desktop-aside">
        <div class="sidebar-content">
          <div class="logo-container">
            <img src="http://www.animeguide.top:8091/themes/theme-heolink/assets/images/logo_cover.jpg" alt="Logo"
                 class="logo-image">
          </div>
          <el-menu
              default-active="2"
              class="el-menu-vertical-demo"
              background-color="#545c64"
              text-color="#fff"
              active-text-color="#ffd04b">
            <div v-for="item in navList" :key="item.id">
              <el-menu-item :index="item.id" @click="scrollTo(item.id)">
                <i class="el-icon-menu"></i>
                <span slot="title">{{ item.navTitle }}</span>
              </el-menu-item>
            </div>
          </el-menu>
        </div>
      </el-aside>
      <el-container class="main-container">
        <el-header class="mobile-header">
          <img src="http://www.animeguide.top:8091/themes/theme-heolink/assets/images/logo_cover.jpg" alt="Logo"
               class="mobile-logo">
          <el-button @click="drawerVisible = true" icon="el-icon-menu" class="mobile-menu-button"></el-button>
        </el-header>
        <el-main>
          <el-card class="hero-card">
            <h1 class="hero-title">xxxx资源网站</h1>
            <p class="hero-subtitle">你的资源导航</p>
          </el-card>
          <el-card>
            <div v-for="item in navList" :key="item.id">
              <div :id="item.id">
                <h3 style="margin: 0">{{ item.navTitle }}</h3>
                <div class="mx-logo-container" style="width: 100%">
                  <el-row :gutter="20">
                    <div v-for="logo in item.urlList" :key="logo.id" class="mx-logo-item">
                      <a :href="logo.url" target="_blank" rel="noopener noreferrer">
                        <el-col :sm="8" :lg="6" style="margin-top: 10px">
                          <el-card shadow="never" style=" height: 70px; display: flex; align-items: center;">
                            <div class="mx-logo" style="display: flex; align-items: center;">
                              <el-avatar :src="logo.cover"
                                         :size="50"></el-avatar>
                              <div class="mx-logo-text" style="margin-left: 25px;">
                                <span>{{ logo.title }}</span>
                              </div>
                            </div>
                          </el-card>
                        </el-col>
                      </a>
                    </div>

                  </el-row>
                </div>
              </div>
              <br>
              <br>
            </div>
          </el-card>
        </el-main>
      </el-container>
    </el-container>
    <el-drawer
        title="菜单"
        :visible.sync="drawerVisible"
        direction="ltr"
        size="80%">
      <el-menu
          default-active="2"
          active-text-color="#ffd04b">

        <div v-for="item in navList" :key="item.id">
          <el-menu-item :index="item.id" @click="scrollTo(item.id)">
            <i class="el-icon-menu"></i>
            <span slot="title">{{item.navTitle}}</span>
          </el-menu-item>
        </div>


      </el-menu>
    </el-drawer>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      drawerVisible: false,
      centerDialogVisible: false,
      navList: [
        {
          id: 1,
          navTitle: 'xxxx资源网站',
          urlList: [
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
          ]
        },
        {
          id: 2,
          navTitle: 'xxxx资源网站',
          urlList: [
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
          ]
        },
        {
          id: 3,
          navTitle: 'xxxx资源网站',
          urlList: [
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
          ]
        },
        {
          id: 5,
          navTitle: 'xxxx资源网站',
          urlList: [
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
            {
              title: '百度',
              url: 'https://www.baidu.com/',
              cover: 'http://gips2.baidu.com/it/u=195724436,3554684702&fm=3028&app=3028&f=JPEG&fmt=auto?w=1280&h=960'
            },
          ]
        },

      ]
    }
  },
  methods: {
    /**
     *
     * @param sectionId
     */
    scrollTo(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        element.scrollIntoView({behavior: 'smooth'});
      }
      this.drawerVisible = false;
    },
  }
}
</script>

<style scoped src="@/static/styles/nav.css"/>
