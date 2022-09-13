<template>
  <div class="m-2">
    <ul class="flex flex-col items-center justify-center">
      <li
        v-for="item in allResources"
        :key="item.id"
        class="
          m-2
          pt-4
          pb-2
          px-4
          rounded-lg
          bg-blue-400
          shadow-lg
          text-white
          flex flex-col
          justify-center
          items-center
          w-3/4
        "
      >
        <!-- Tajuk & deleteButon -->
        <div class="flex justify-between items-center w-full">
          <h1 class="text-xl text-black font-semibold">{{ item.title }}</h1>
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
        <div class="flex flex-row w-full mt-4 mb-2">
          <p class="text-slate-900">{{ item.description }}</p>
        </div>
        <!-- Link to website  -->
        <div
          class="
            flex flex-row
            justify-start
            items-center
            w-full
            mt-1
            mb-1
            hover:underline hover:underline-offset-2
            text-blue-900
            font-semibold
            hover:text-purple-800 hover:cursor-pointer
          "
        >
          <a class="">View Resources </a><link-icon />
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import { BIconTrashFill, BIconLink45deg } from "bootstrap-icons-vue";
export default {
  components: {
    BIconTrashFill,
    linkIcon: BIconLink45deg,
  },
  inject: ["allResources"],
};
</script>


<style>
</style>