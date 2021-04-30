<template>
  <div class="tabPane">
    <button v-for="tab in tabs"
            :key="tab"
            :class="{ active: currentTab === tab }"
            @click="switchTab(tab)"
    >
      {{ tab }}
    </button>
    <keep-alive>
      <component :is="currentTab" class="tab"/>
    </keep-alive>
  </div>

</template>

<script>
  import Tab1 from './components/Tab1.vue'
  import Tab2 from './components/Tab2.vue'

  export default {
    name: 'App',
    components: {
      Tab1, Tab2
    },

    data() {
      return {
        tabs: ["Tab1", "Tab2"],
        currentTab: "Tab1",
      }
    },

    methods: {
      switchTab(id) {
        console.log(`App.vue: switchTab(${id})`);
        this.currentTab = id;
      }
    },

    watch: {
      currentTab() {
        console.log(`App.vue: currentTab=${this.currentTab}`);
      }
    }

  }
</script>

<style scoped>
  button {
    border: solid gray;
    border-width: 1px 1px 0 1px;
    border-radius: .25em .25em 0 0;
  }
  .active {
    background-color: darkgray;
  }

  .tab {
    border: solid gray;
    border-width: 1px;
  }
</style>
