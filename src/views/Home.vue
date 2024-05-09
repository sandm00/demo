<template>
  <div class="home">
    <el-button type="primary" v-for="(item, index) in btnList" :key="index" @click="handleClick(item)">{{ item.name }}</el-button>
    {{ $t('hello.title') }}
    <router-link to="/about">about</router-link>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      btnList: [
        {
          name: '中文',
          type: 'zh'
        },
        {
          name: 'English',
          type: 'en'
        },
        {
          name: 'Español',
          type: 'es'
        },
        {
          name: '日本語',
          type: 'ja'
        }
      ]
    }
  },
  methods: {
    handleClick(lang) {
      this.$i18n.locale = lang.type
      this.$store.dispatch('app/setLanguage', lang.type)
      this.$message({
        message: lang.name + ':' + 'Switch Language Success',
        type: 'success'
      })
    }
  },
  components: {}
}
</script>
