<template>
  <nav
    class="
      bg-[#242481]
      w-full
      flex
      items-center
      justify-between
      text-white
      p-4
      mx-auto
    "
  >
    <a
      class="
        inline-flex
        items-center
        justify-center
        w-10
        h-10
        bg-gray-100
        rounded-lg
      "
      href="/"
    >
      👋
    </a>
    <h1 class="text-xl font-bold">V Learning Hub</h1>

    <ul class="flex items-center text-sm font-medium space-x-2">
      <li class="hidden lg:block">
        <a class="px-3 py-2 rounded-lg" href="/"> Home </a>
      </li>

      <li><a class="px-3 py-2 rounded-lg" href=""> Projects </a></li>

      <li>
        <a
          class="inline-flex items-center px-3 py-2 rounded-lg"
          href=""
          target="_blank"
        >
          External
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            class="ml-1.5 w-4 h-4"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
            ></path>
          </svg>
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {};
</script>

<style>
</style>