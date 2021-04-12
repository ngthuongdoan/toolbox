<template>
  <el-container>
    <el-header>
      <el-menu
          :default-active="activeIndex"
          active-text-color="#ffd04b"
          background-color="#545c64"
          class="el-menu-demo"
          mode="horizontal"
          text-color="#fff"
          @select="handleSelect">
        <el-menu-item index="1">Home</el-menu-item>
        <el-menu-item index="2">Tools</el-menu-item>
        <el-menu-item index="3">Contact</el-menu-item>
      </el-menu>
    </el-header>
    <el-main>
      <el-row :gutter="20">
        <el-col :span="6" v-for="f in feature" v-bind:key="f.name">
          <div class="grid-content bg-purple">
            <el-card class="box-card">
              <div class="text item">
                {{f.name}}
              </div>
            </el-card>
          </div>
        </el-col>
      </el-row>
    </el-main>
  </el-container>
</template>

<script lang="ts">
import {defineComponent} from 'vue'
import feature from "@/config/feature.json"

export default defineComponent({
  name: 'App',
  data() {
    return {
      activeIndex: '1',
      feature
    };
  },
  methods: {
    handleSelect(key: string, keyPath: Array<String>) {
      console.log(key, keyPath);
    }
  },
  components: {}
})
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.el-main {
  background-color: #E9EEF3;
  color: #333;
  text-align: center;
  line-height: 160px;
  height: calc(100vh - 60px) !important;
}

.el-header {
  background-color: #B3C0D1;
  color: #333;
  text-align: center;
  line-height: 60px;
  padding: 0 !important;
}

.el-row {
  margin-bottom: 20px;

  &:last-child {
    margin-bottom: 0;
  }
}

.el-col {
  border-radius: 4px;
}

.bg-purple-dark {
  background: #99a9bf;
}

.bg-purple {
  background: #d3dce6;
}

.bg-purple-light {
  background: #e5e9f2;
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}

.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}

.text {
  font-size: 14px;
}

.item {
  padding: 18px 0;
}

</style>