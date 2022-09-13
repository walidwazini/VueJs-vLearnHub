<template>
  <div class="bg-green-400 m-2">
    <h1 class="text-xl text-white font-bold">This is strored resources</h1>
    <ul class="flex flex-col items-center justify-center">
      <li
        v-for="item in allResources"
        :key="item.id"
        class="
          m-2
          py-4
          px-4
          bg-blue-400
          shadow-md
          text-white
          flex flex-col
          justify-center
          items-center
          w-1/2
        "
      >
        <!-- Tajuk & deleteButon -->
        <div class="flex justify-between items-center w-full">
          <h1 class="text-xl text-black">{{ item.title }}</h1>
          <button
            class="
              text-red-700
              font-semibold
              hover:bg-red-300
              transition
              duration-300
              rounded-full
              p-2
            "
          >
            <BIconTrashFill />
          </button>
        </div>
        <!-- Info  -->
        <div>
          {{ item.description }}
        </div>
        <!-- Link to website  -->
        <div>View Resources</div>
      </li>
    </ul>
  </div>
</template>

<script>
import { BIconTrashFill } from "bootstrap-icons-vue";
export default {
  components: {
    BIconTrashFill,
  },
  inject: ["allResources"],
};
</script>


<style>
</style>