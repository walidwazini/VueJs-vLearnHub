<template>
  <div
    class="
      min-h-[10vh]
      bg-[#25258f]
      mt-5
      mb-10
      mx-14
      pb-4
      rounded-md
      flex flex-col
      justify-center
      items-center
    "
  >
    <div class="w-[370px] mt-5 my-2">
      <label class="font-xl font-semibold text-white">Title</label>
      <input class="w-full p-3 mt-1 text-sm border-2 border-gray-200 rounded" />
    </div>
    <div class="w-[370px] my-2">
      <label class="font-xl font-semibold text-white">Description</label>
      <textarea
        class="w-full p-3 mt-1 text-sm border-2 border-gray-200 rounded"
      />
    </div>
    <div class="w-[370px] my-2">
      <label class="font-xl font-semibold text-white">Website Link</label>
      <div class="flex">
        <input class="w-full p-3 text-xs rounded-l-md h-5" />
        <span
          class="
            flex
            items-center
            px-3
            pointer-events-none
            sm:text-sm
            rounded-r-md
            bg-slate-700
          "
          >🌐</span
        >
      </div>
    </div>
    <div class="w-[370px] my-2">
      <label class="font-xl font-semibold text-white">Image URL</label>
      <div class="flex">
        <input class="w-full p-3 text-xs rounded-l-md h-5" />
        <span
          class="
            flex
            items-center
            px-3
            pointer-events-none
            sm:text-sm
            rounded-r-md
            bg-slate-700
          "
          >🔗</span
        >
      </div>
    </div>

    <!-- <fieldset className="w-[370px] mt-2 space-y-1 dark:text-gray-100">
      <label for="files" className="block text-sm font-medium"
        >Image File</label
      >
      <div className="flex">
        <input
          type="file"
          name="files"
          id="files"
          className="px-8 py-12 border-2 border-dashed rounded-md dark:border-gray-700 dark:text-gray-400 dark:bg-gray-800"
        />
      </div>
    </fieldset> -->

    <button
      class="
        px-4
        py-2
        mt-4
        mb-4
        text-sm
        font-medium
        tracking-wide
        text-white
        capitalize
        transition-colors
        duration-300
        transform
        bg-green-500
        rounded-md
        sm:mx-2
        hover:bg-green-300
        focus:outline-none focus:bg-blue-600
      "
    >
      Add New
    </button>
  </div>
</template>

<script>
export default {
  data() {},
};
</script>

<style>
</style>