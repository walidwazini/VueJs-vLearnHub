<template>
  <div class="m-2">
    <ul class="flex flex-col items-center justify-center">
      <li
        v-for="item in allResources"
        :key="item.id"
        class="
          m-2
          pb-4
          rounded-lg
          bg-blue-600
          shadow-lg
          text-white
          flex flex-col
          justify-center
          items-center
          w-3/4
        "
      >
        <!-- Tajuk & deleteButon -->
        <div class="realtive w-full">
          <img
            :src="item.image || imageDef"
            alt=""
            class="object-cover object-center w-full rounded-t-md h-28"
          />
          <div
            class="
              relative
              top-[-4rem]
              left-[2rem]
              flex
              justify-between
              w-[560px]
            "
          >
            <h1
              class="text-xl hover:text-2xl shadow-sm text-black font-semibold"
            >
              {{ item.title }}
            </h1>
            <button
              @click="deleteItem(item.id)"
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
        </div>
        <!-- Info  -->
        <div class="flex flex-row w-full mb-1 px-10 mt-[-20px]">
          <p class="text-white">{{ item.description }}</p>
        </div>
        <!-- Link to website  -->
        <div
          class="
            flex flex-row
            justify-start
            items-center
            w-full
            mt-3
            mb-1
            px-10
            hover:underline hover:underline-offset-2
            font-semibold
            hover:cursor-pointer
          "
        >
          <div
            class="
              min-w-max
              flex
              py-1
              px-3
              rounded-md
              bg-white
              text-slate-800
              hover:bg-slate-400
              transition
              duration-300
              shadow-sm
              border-white
              hover:border-red-500
            "
          >
            <a class="" v-bind:href="item.link">Website</a><link-icon />
          </div>
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
  data() {
    return {
      imageDef:
        "https://images.unsplash.com/photo-1586125674857-4eb86880905d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
      rand: 1,
    };
  },
  inject: ["allResources", "deleteItem"],
  methods: {
    getImage(pic) {
      return require(pic);
    },
  },
};
</script>


<style>
</style>