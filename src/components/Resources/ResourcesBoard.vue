<template>
  <!-- CARD  -->
  <div
    class="
      rounded-xl
      shadow-md
      w-1/2
      h-32
      bg-blue-900
      flex flex-row
      justify-start
      items-center
      px-4
    "
  >
    <BaseButton @click="setSelectedTab('stored-resource')" :mode="resBtnMode"
      >Stored Resources</BaseButton
    >
    <BaseButton @click="setSelectedTab('add-resource')" :mode="addBtnMode"
      >Add Resource</BaseButton
    >
  </div>
  <div class="mt-14 w-1/2 h-52 bg-red-600">
    <KeepAlive>
      <component :is="selectedTab"> </component>
    </KeepAlive>
  </div>
</template>

<script>
import BaseButton from "../base/BaseButton.vue";
export default {
  components: { BaseButton },
  data() {
    return {
      selectedTab: "stored-resource",
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official VUe Js documentation",
          link: "https://vuejs.org",
        },
        {
          id: "search-engine",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
      ],
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
  computed: {
    resBtnMode() {
      return this.selectedTab === "stored-resource"
        ? "text-white underline underline-offset-4 "
        : null;
    },
    addBtnMode() {
      return this.selectedTab === "add-resource"
        ? "text-white underline underline-offset-4"
        : null;
    },
  },
};
</script>

<style>
</style>