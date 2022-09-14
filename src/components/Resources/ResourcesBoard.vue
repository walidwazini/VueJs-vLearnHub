<template>
  <!-- CARD  -->

  <BaseCard :extraClass="tabCardClass">
    <BaseButton @click="setSelectedTab('stored-resources')" :mode="resBtnMode"
      >Stored Resources</BaseButton
    >
    <BaseButton @click="setSelectedTab('add-resource')" :mode="addBtnMode"
      >Add Resource</BaseButton
    ></BaseCard
  >
  <div class="mt-10 w-1/2 h-auto">
    <KeepAlive>
      <div
        v-if="selectedTab === 'stored-resources'"
        class="relative mt-5 ml-5 text-2xl text-white"
      >
        <archieve-icon />
      </div>
      <div
        v-else-if="selectedTab === 'add-resource'"
        class="relative mt-5 ml-5 text-2xl text-white"
      >
        <add-new-icon />
      </div>
    </KeepAlive>
    <KeepAlive>
      <component :is="selectedTab"> </component>
    </KeepAlive>
  </div>
</template>

<script>
import { BIconArchive, BIconFileEarmarkPlus } from "bootstrap-icons-vue";

import BaseButton from "../base/BaseButton.vue";
import BaseCard from "../base/BaseCard.vue";
import AddResource from "./AddResource.vue";
import StoredResources from "./StoredResources.vue";
export default {
  components: {
    BaseButton,
    BaseCard,
    StoredResources,
    AddResource,
    archieveIcon: BIconArchive,
    addNewIcon: BIconFileEarmarkPlus,
  },
  data() {
    return {
      // selectedTab: "add-resource" or "stored-resources",
      // selectedTab: StoredResources,
      selectedTab: AddResource,
      resourcesList: [
        {
          id: "official-guide",
          title: "Vue JS",
          description: "The official VueJS documentation.",
          image:
            "https://images.ctfassets.net/aq13lwl6616q/1l0V8UVa67J2sBaci1BrWr/67b883dc9079ba82b016edfc8ce9a1c1/Complete_Vue_Zero_to_Mastery.png",
          link: "https://vuejs.org",
        },
        {
          id: "search-engine-0-",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },

        {
          id: "react-js-382",
          title: "React JS",
          description: "Learn how to search solution productively",
          image:
            "https://ares.decipherzone.com/blog-manager/uploads/banner_webp_da06d145-93f9-4df9-8c7e-1e2c332c3a4a.webp",
          link: "https://google.com",
        },
        {
          id: "search-engineada",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
        {
          id: "search-enginesdfsdf",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
        {
          id: "search-e",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
        {
          id: "search-engine12",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
        {
          id: "search-engine34",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
        {
          id: "search-engine56",
          title: "Google",
          description: "Learn how to search solution productively",
          link: "https://google.com",
        },
      ],
    };
  },
  provide() {
    return {
      allResources: this.resourcesList,
      deleteItem: this.removeResource,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    removeResource(resId) {
      const resIndex = this.resourcesList.findIndex((res) => res.id === resId);

      this.resourcesList.splice(resIndex, 1);
    },
  },
  computed: {
    tabCardClass() {
      return "h-28";
    },
    // We use these two to change the content of the tab
    resBtnMode() {
      return this.selectedTab === "stored-resources"
        ? "text-white underline underline-offset-4 "
        : null;
    },
    addBtnMode() {
      // return this.selectedTab === AddResource
      return this.selectedTab === "add-resource"
        ? "text-white underline underline-offset-4"
        : null;
    },
  },
};
</script>

<style>
</style>