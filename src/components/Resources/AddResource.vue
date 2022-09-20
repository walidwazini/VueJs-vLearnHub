<template>
  <form
    @submit.prevent="submitNew"
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
      {{ VUE_APP_FIREBASE }}
      <label class="font-xl font-semibold text-white">Title</label>
      <input
        type="text"
        ref="titleInput"
        class="w-full p-3 mt-1 text-sm border-2 border-gray-200 rounded"
      />
    </div>
    <div class="w-[370px] my-2">
      <label class="font-xl font-semibold text-white">Description</label>
      <textarea
        ref="descInput"
        type="text"
        rows="2"
        class="w-full p-3 mt-1 text-sm border-2 border-gray-200 rounded"
      />
    </div>
    <div class="w-[370px] my-2">
      <label class="font-xl font-semibold text-white">Website Link</label>
      <div class="flex">
        <input
          type="url"
          ref="webLinkInput"
          class="w-full p-3 text-xs rounded-l-md h-5"
        />
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
        <input
          type="url"
          ref="imgLinkInput"
          class="w-full p-3 text-xs rounded-l-md h-5"
        />
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
      type="submit"
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
  </form>
</template>

<script>
import FIREBASE_URL from "../../firebase";

export default {
  data() {
    return {
      inputValid: false,
    };
  },
  inject: ["onAddResource"],
  methods: {
    submitNew() {
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDesc = this.$refs.descInput.value;
      const enteredWebUrl = this.$refs.webLinkInput.value;
      const enteredImgUrl = this.$refs.imgLinkInput.value;

      const conditionOne =
        enteredTitle.trim() === "" ||
        enteredDesc.trim() === "" ||
        enteredWebUrl.trim() === "" ||
        enteredImgUrl.trim() === "";

      if (conditionOne) {
        this.$inputValid = true;
        return;
      }
      fetch(FIREBASE_URL, {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({
          title: enteredTitle,
          description: enteredDesc,
          web: enteredWebUrl,
          image: enteredImgUrl,
        }),
      })
        .then((response) => {
          if (response.ok) {
            // ..
          } else {
            throw new Error("Could not save data");
          }
        })
        .catch((error) => {
          console.log(error);
          // this.errorSendingData = 'Sending data failed. Something is wrong.';
        });
      this.$refs.titleInput.value = "";
      this.$refs.descInput.value = "";
      this.$refs.webLinkInput.value = "";
      this.$refs.imgLinkInput.value = "";
    },
    submitHandler() {
      // const enteredTitle = this.$refs.titleInput.value;
      // const enteredDesc = this.$refs.descInput.value;
      // const enteredWebUrl = this.$refs.webLinkInput.value;
      // const enteredImgUrl = this.$refs.imgLinkInput.value;

      // const conditionOne =
      //   enteredTitle.trim() === "" ||
      //   enteredDesc.trim() === "" ||
      //   enteredWebUrl.trim() === "" ||
      //   enteredImgUrl.trim() === "";

      // if (conditionOne) {
      //   this.$inputValid = true;
      //   return;
      // }
      // this.onAddResource(
      //   enteredTitle,
      //   enteredDesc,
      //   enteredWebUrl,
      //   enteredImgUrl
      // );
      this.$refs.titleInput.value = "";
      this.$refs.descInput.value = "";
      this.$refs.webLinkInput.value = "";
      this.$refs.imgLinkInput.value = "";
    },
  },
};
</script>

<style>
</style>